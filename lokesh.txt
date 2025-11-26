# Nextcloud Server Connectivity Test
$server = "10.121.51.75"
$url = "http://$server"

Write-Host "Testing connectivity to $server..." -ForegroundColor Cyan

# Step 1: Ping test
$ping = Test-Connection -ComputerName $server -Count 2 -Quiet

if ($ping) {
    Write-Host "✅ Ping successful! The server is reachable on the network." -ForegroundColor Green

    # Step 2: Check if web service (Nextcloud) responds
    try {
        $response = Invoke-WebRequest -Uri $url -UseBasicParsing -TimeoutSec 5
        if ($response.StatusCode -eq 200) {
            Write-Host "🌐 Web service is responding. Nextcloud might be running." -ForegroundColor Green
        } else {
            Write-Host "⚠️ Web server responded, but not with status 200. Code: $($response.StatusCode)" -ForegroundColor Yellow
        }
    }
    catch {
        Write-Host "❌ Could not reach the web service at $url" -ForegroundColor Red
    }
} 
else {
    Write-Host "❌ Ping failed! The server is not reachable on your current network." -ForegroundColor Red
    Write-Host "`nPossible reasons:`n- You are not connected to the same local network.`n- The server is turned off or disconnected.`n- A firewall is blocking access." -ForegroundColor Yellow
}

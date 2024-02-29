# Maakt een arraylist aan om namen te storen
$names = New-Object System.Collections.ArrayList

# Prompt de gebruiker om namen toe te voegen totdat je 'klaar'zegt
Write-Host "Voeg namen voor de Sinterklaasloterij (typ 'klaar' wanneer je klaar bent):"
do {
    $name = Read-Host "Voeg een naam toe"
    if ($name -ne "klaar") {
        $names.Add($name) | Out-Null # Voegt naam toe aan de arraylist
    }
} until ($name -eq "klaar") # Totdat je 'klaar'zegt, gaat de script verder

# Checkt of het aantal even is of oneven door het aantal gedeeld door 2 en als het 1 is, dan is het oneven
if ($names.Count % 2 -eq 1) {
    Write-Host "Aantal deelnemers is niet even! Zorg dat het aantal even is!"
}
else {
    # Deelnemers worden random gematched
    Write-Host "Deelnemers worden gematched..."
    while ($names.Count -gt 0) {
        $giverIndex = Get-Random -Minimum 0 -Maximum $names.Count # selecteert random naam in de array, aan de had van aantal
        $giver = $names[$giverIndex] # giver is een naam met de random count van giverindex
        $names.RemoveAt($giverIndex) # Verwijder gever om dubbel te voorkomen

        $recipientIndex = Get-Random -Minimum 0 -Maximum $names.Count
        $recipient = $names[$recipientIndex]
        $names.RemoveAt($recipientIndex) # Verwijder ontvanger om dubbel te voorkomen

        Write-Host "$giver heeft $recipient getrokken!"
    }
}

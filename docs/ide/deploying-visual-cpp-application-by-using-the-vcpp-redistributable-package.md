---
title: "Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe von Visual C++ Redistributable Package"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exemplarische Vorgehensweise, Bereitstellen einer Visual C++-Anwendung mit dem Redistributable Package"
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe von Visual C++ Redistributable Package
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel wird schrittweise beschrieben, wie Visual C\+\+ Redistributable Package verwendet, um eine Visual C\+\+\-Anwendung bereitgestellt.  
  
## Vorbereitungsmaßnahmen  
 Sie müssen diese Komponenten haben, um diese exemplarischen Vorgehensweise sind:  
  
-   Ein Computer, der Visual Studio installiert ist.  
  
-   Einen zusätzlichen Computer ohne die Visual C\+\+\-Bibliotheken  
  
### So führen Sie Visual C\+\+ Redistributable Package verwenden, um eine Anwendung bereitzustellen  
  
1.  Erstellen Sie eine MFC\-Anwendung auf, indem Sie den ersten drei Schritten in [Walkthrough: Deploying a Visual C\+\+ Application By Using a Setup Project](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md) folgen.  
  
2.  Erstellen Sie eine Datei, und nennen Sie diese setup.bat und fügen Sie die folgenden Befehle hinzu.  Ändern Sie `MyMFCApplication` auf den Namen des Projekts.  
  
    ```  
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  Erstellen Sie eine selbstextrahierende Setupdatei:  
  
    1.  Geben Sie an einer Eingabeaufforderung oder im Fenster, **Ausführen** Ausführung iexpress.exe.  
  
    2.  Ausgewähltes **Neue Direktivendatei für Selbstextrahierung erstellen** und dann die Schaltfläche **Weiter** aus.  
  
    3.  Ausgewähltes **Dateien extrahieren und Installationsbefehl ausführen** und wählen dann **Weiter** aus.  
  
    4.  Geben Sie im Textfeld den Namen der MFC\-Anwendung ein und klicken Sie dann **Weiter** aus.  
  
    5.  Auf der Seite wählen **Eingabeaufforderung zur Bestätigung** ausgewähltes **Keine Eingabeaufforderung** und dann **Weiter** aus.  
  
    6.  Auf der Seite wählen **Lizenzvertrag** ausgewähltes **Keine Lizenz anzeigen** und dann **Weiter** aus.  
  
    7.  Klicken Sie auf der Seite **Paketdateien** fügen Sie die folgenden Dateien hinzu und wählen Sie dann **Weiter** aus.  
  
        -   Ihre MFC\-Anwendung \(EXE\-Datei\).  
  
        -   vcredist\_x86.exe.  Diese Datei wird in \\Programme\\Microsoft SDKs\\Windows\\v7.0A\\Bootstrapper\\Packages\\vcredist\_x86\\ isoliert.  
  
        -   Die Datei "setup.bat", die Sie im vorherigen Schritt erstellt haben.  
  
    8.  Klicken Sie auf der Seite im Textfeld **Zu startendes Programm installierenProgramm installieren** Geben Sie die folgende Befehlszeile ein, und wählen Sie dann **Weiter** aus.  
  
         **cmd.exe \/c "setup.bat"**  
  
    9. Auf der Seite wählen **Fenster einblenden** ausgewähltes **Standard** und dann **Weiter** aus.  
  
    10. Auf der Seite wählen **Abgeschlossene Meldung** ausgewähltes **Keine Meldung** und dann **Weiter** aus.  
  
    11. **Paketname und Optionen** auf der Seite einen Namen für die selbstextrahierende Setupdatei ein, wählen Sie die Option **Dateien mit einem langen Dateinamen im Paket speichern** aus, und wählen Sie dann **Weiter** aus.  Das Ende des Dateinamens muss Setup.exe\-for Beispiel, MyMFCApplicationSetup.exe sein.  
  
    12. Auf der Seite wählen **Neustart konfigurieren** ausgewähltes **Kein Neustart** und dann **Weiter** aus.  
  
    13. Auf der Seite wählen **Direktive für Selbstextrahierung speichern** ausgewähltes **Datei für Selbstextrahierungsrichtlinie speichern** und dann **Weiter** aus.  
  
    14. Klicken Sie auf der Seite **Paket erstellen** wählen Sie **Weiter** aus.  
  
4.  Testen Sie die selbstextrahierende Setupdatei auf dem anderen Computer, der die Visual C\+\+\-Bibliotheken nicht vorhanden sind:  
  
    1.  Klicken Sie auf dem anderen Computer laden Sie eine Kopie der Setupdatei herunter, und installieren Sie sie dann, indem Sie sie und nach den Schritten ausführen, die er bereitstellt.  
  
    2.  Führen Sie die MFC\-Anwendung aus.  
  
         Von der selbstextrahierenden Setupdatei wird die MFC\-Anwendung installiert, die sich in dem in Schritt 2 angegebenen Ordner befindet.  Die Anwendung wird erfolgreich ausgeführt, da das Visual C\+\+ Redistributable Package\-Installationsprogramm in der selbstextrahierenden Setupdatei enthalten ist.  
  
        > [!IMPORTANT]
        >  Bestimmen, welche Version der Laufzeit installiert ist, die Installationsprogrammüberprüfungen der Registrierungsschlüssel \\HKLM\\SOFTWARE\\Microsoft\\VisualStudio\\11.0\\VC\\Runtimes\\\[Plattform\].  Wenn die derzeit installierte Version neuer als die Version ist, die das Installationsprogramm versucht, zu installieren, gibt das Installationsprogramm Erfolg, ohne die vorherige Version zu installieren zurück und ermöglicht eine Nachbuchung auf der installierten Programmseite in der Systemsteuerung.  
  
## Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)
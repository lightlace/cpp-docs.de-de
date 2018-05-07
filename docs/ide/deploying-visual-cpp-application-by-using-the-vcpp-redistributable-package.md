---
title: Bereitstellen einer App das Redistributable Package (C++) mit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthrough, deploying a Visual C++ application by using the redistributable package
ms.assetid: e59becbf-b8c6-4c8e-bab3-b69cc1ed3e5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37bba00efdf0368973fa4ffbac1cbc6bb6298ce1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-the-visual-c-redistributable-package"></a>Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe von Visual C++ Redistributable Package
Dieser Artikel beschreibt, wie der Visual C++ Redistributable Package eine Visual C++-Anwendung bereitstellen.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Diese Komponenten zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie:  
  
-   Ein Computer, der Visual Studio installiert ist.  
  
-   Ein zusätzlicher Computer, die über keinen Visual C++-Bibliotheken.  
  
### <a name="to-use-the-visual-c-redistributable-package-to-deploy-an-application"></a>Verwenden Sie das Visual C++ Redistributable Package zum Bereitstellen einer Anwendung  
  
1.  Erstellen Sie eine MFC-Anwendung mithilfe der ersten drei Schritte im [Exemplarische Vorgehensweise: Bereitstellen einer Visual C++-Anwendung mithilfe eines Setup-Projekts](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
2.  Erstellen Sie eine Datei, nennen Sie sie "Setup.bat", und fügen Sie die folgenden Befehle hinzu. Änderung `MyMFCApplication` auf den Namen des Projekts.  
  
    ```cmd
    @echo off  
    vcredist_x86.exe  
    mkdir "C:\Program Files\MyMFCApplication"  
    copy MyMFCApplication.exe "C:\Program Files\MyMFCApplication"  
    ```  
  
3.  Erstellen Sie eine selbstextrahierende Setupdatei:  
  
    1.  An der Eingabeaufforderung oder in der **ausführen** Fenster iexpress.exe ausführen.  
  
    2.  Wählen Sie **neue SED-Datei erstellen** und wählen Sie dann die **Weiter** Schaltfläche.  
  
    3.  Wählen Sie **Extrahieren von Dateien, und führen Sie einen Installationsbefehl** und wählen Sie dann **Weiter**.  
  
    4.  Geben Sie im Textfeld den Namen der MFC-Anwendung, und wählen Sie dann **Weiter**.  
  
    5.  Auf der **bestätigungsaufforderung** Seite **keine Eingabeaufforderung** und wählen Sie dann **Weiter**.  
  
    6.  Auf der **Lizenzvertrag** Seite **Lizenz nicht anzeigen** und wählen Sie dann **Weiter**.  
  
    7.  Auf der **Dateien verpackt** Seite, fügen Sie die folgenden Dateien hinzu, und wählen Sie dann **Weiter**.  
  
        -   MFC-Anwendung (.exe-Datei).  
  
        -   VCRedist_x86.exe. Diese Datei befindet sich unter \Programme\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\vcredist_x86\\.  
  
        -   Die Datei "Setup.bat", die Sie in einem vorhergehenden Schritt erstellt haben.  
  
    8.  Auf der **Installationsprogramm zu startender** Seite in der **Installationsprogramm** Textfeld, geben Sie die folgende Befehlszeile, und wählen Sie dann **Weiter**.  
  
         **cmd.exe/c "setup.bat"**  
  
    9. Auf der **Fenster** Seite **Standard** und wählen Sie dann **Weiter**.  
  
    10. Auf der **Abschlussnachricht** Seite **keine Meldung** und wählen Sie dann **Weiter**.  
  
    11. Auf der **Paketnamen und Optionen** Seite, geben Sie einen Namen für die selbstextrahierende Setupdatei an, wählen die **Speichern von Dateien mit langen Dateinamen im Paket** aus, und wählen Sie dann **Weiter**. Das Ende des Dateinamens muss Setup.exe—for beispielsweise MyMFCApplicationSetup.exe sein.  
  
    12. Auf der **Neustart konfigurieren** Seite **kein Neustart** und wählen Sie dann **Weiter**.  
  
    13. Auf der **SED speichern** Seite **speichern Self Extraction Directive (SED) Datei** und wählen Sie dann **Weiter**.  
  
    14. Auf der **Erstellung eines Pakets** Seite **Weiter**.  
  
4.  Testen Sie selbstextrahierende Setupdatei auf dem anderen Computer, der nicht über die Visual C++-Bibliotheken verfügt:  
  
    1.  Klicken Sie auf dem anderen Computer Laden Sie eine Kopie der Datei, und installieren Sie sie durch Ausführen und die Schritte, die es bereitstellt.  
  
    2.  Führen Sie die MFC-Anwendung.  
  
         Die selbstextrahierende Setupdatei installiert die MFC-Anwendung, die im Ordner "" ist, die Sie in Schritt 2 angegeben. Die Anwendung wird erfolgreich ausgeführt, da Visual C++ Redistributable Package-Installationsprogramm in die selbstextrahierende Setupdatei enthalten ist.  
  
        > [!IMPORTANT]
        >  Um zu bestimmen, welche Version der Laufzeit installiert ist, prüft das Installationsprogramm die Registry Key \HKLM\SOFTWARE\Microsoft\VisualStudio\11.0\VC\Runtimes\\[Plattform]. Wenn die derzeit installierte Version neuer als die Version, der das Installationsprogramm versucht ist, installieren, wird das Installationsprogramm Erfolgswert zurück, ohne die ältere Version installieren, und bewirkt, dass einen weiteren Eintrag auf der Seite "installierten Programme" in der Systemsteuerung.  
  
## <a name="see-also"></a>Siehe auch  
 [Bereitstellungsbeispiele](../ide/deployment-examples.md)
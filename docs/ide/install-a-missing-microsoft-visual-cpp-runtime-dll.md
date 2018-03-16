---
title: Installieren Sie einen fehlenden Microsoft Visual C++-Runtime-DLL | Microsoft Docs
description: Zum Suchen und Installieren von Visual C++-Laufzeit-DLLs fehlen.
ms.date: 03/13/2018
ms.topic: article
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6410c9753577852989172121d01c9d768f5373b3
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/16/2018
---
# <a name="install-a-missing-microsoft-visual-c-runtime-dll"></a>Installieren Sie einen fehlenden Microsoft Visual C++-Runtime-DLL

Häufig mithilfe von Microsoft Visual C++ geschriebene Programme erfordern einige zusätzliche Visual C++ Runtime Library-Dateien oder DLLs, ausgeführt. Diese Laufzeit DLLs stehen in einem *Redistributable Package*, eine Bibliothek Datei-Installationsprogramm für jede Version von Visual C++. Das verteilbare Paket erforderlich, die für jedes Programm sollte vom Installationsprogramm enthalten sein. Wenn sie nicht der Fall ist, können in einigen Fällen verteilbares Paket zu installieren und einen Systemfehler beheben, wenn Sie das Programm ausführen.

Sie können feststellen, dass ein Programm eine Visual C++-Runtime-DLL fehlt, wenn einen Systemfehler erhalten, wenn das Programm zu starten, die besagt, etwas dass wie "das Programm starten kann, da" vcruntime140.dll "auf Ihrem Computer nicht vorhanden ist". Häufig kann dieses Problem behoben werden, durch die Deinstallation des Programms, und klicken Sie dann erneut zu installieren. Es wird dringend zuerst versuchen, diesen Schritt, bevor eine beliebige andere von potenziellen Fehlerbehebungen.

In einigen Fällen ist das verteilbare Paket von einem Programm installiert nicht mehr aktuell. Microsoft stellt aktualisierte Versionen der Laufzeit DLLs zur Verfügung von Zeit zu Zeit zum Beheben von Fehlern und Sicherheitsprobleme. Um Ihr Computer sicher und korrekt zu halten, ist es ratsam, das neueste Update für alle DLL-Laufzeit verwenden. Überprüfen Sie, wenn eine aktualisierte Installationsprogramm verfügbar für das Programm, das dieses Update für die Sie bereitstellen kann. Wenn vorhanden ist, verwenden Sie aktualisierte Installationsprogramm, um das Programm neu zu installieren.

Wenn Neuinstallation des Programms den Fehler behoben nicht vornehmen, klicken Sie dann das Installationsprogramm fehlerhaft oder beschädigt werden kann, oder der Common Language Runtime-DLLs auf dem Computer ist möglicherweise beschädigt. Versuchen Sie, eine neue Kopie des Installationsprogramms für das Programm herunterladen und verwenden es zuerst installieren. Wenn dies nicht funktioniert, oder in einem Installationsprogramm ist nicht verfügbar, kann dann es sinnvoll sein, überprüfen Sie die Microsoft Visual C++ Redistributable-Installationen auf dem Computer sein.

Diese Tabelle zeigt eine Liste der DLLs, die in eine oder mehrere verteilbare Pakete sowie Links zum Herunterladen einer Kopie des verteilbaren Pakets enthalten sind. Bevor Sie eine neue Kopie des verteilbares Paket heruntergeladen haben, sollten Sie sehen, wenn Sie eine vorhandene Installation zu reparieren.

|Fehlende DLL  |Verteilbare Paket  |
|---------|---------|
|atl80.dll<br />msvcm80.dll<br />msvcp80.dll<br />msvcr80.dll<br />mfc80.dll<br />mfc80u.dll<br />mfcm80.dll<br />mfcm80u.dll|[Microsoft Visual C++ 2005 Redistributable (x86)](https://www.microsoft.com/en-us/download/details.aspx?id=5638)<br />[Microsoft Visual C++ 2005 Redistributable Package (x64)](https://www.microsoft.com/en-us/download/details.aspx?id=18471)<br />[MFC-Sicherheitsupdate für Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=26347)|
|atl90.dll<br />msvcr90.dll<br />msvcm90.dll<br />msvcp90.dll<br />mfc90.dll<br />mfc90u.dll<br />mfcmifc80.dll<br />mfcm90.dll<br />mfcm90u.dll|[Microsoft Visual C++ 2008 Redistributable - x86](https://www.microsoft.com/en-us/download/details.aspx?id=5582)<br />[Microsoft Visual C++ 2008 Redistributable - x64](https://www.microsoft.com/en-us/download/details.aspx?id=2092)<br />[MFC-Sicherheitsupdate für Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=26368)|
|atl100.dll<br />msvcr100.dll<br />msvcp100.dll<br />msdia71.dll<br />vcomp100.dll<br />mfc100.dll<br />mfc100u.dll<br />mfcmifc80.dll<br />mfcm100.dll<br />mfcm100u.dll|[Microsoft Visual C++ 2010 x86 Redistributable](https://www.microsoft.com/en-us/download/details.aspx?id=8328)<br />[Microsoft Visual C++ 2010 x64 Redistributable](https://www.microsoft.com/en-us/download/details.aspx?id=13523)<br />[MFC-Sicherheitsupdate für Microsoft Visual C++ 2010 Service Pack 1 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=26999)|
|atl110.dll<br />msvcr110.dll<br />msvcp110.dll<br />mfc110.dll<br />mfc110u.dll<br />mfcmifc80.dll<br />mfcm110.dll<br />mfcm110u.dll<br />concrt110.dll<br />vccorlib110.dll<br />vcamp110.dll<br />vcomp110.dll|[Microsoft Visual C++ 2012 Redistributable (für Visual Studio 2012 Update 4)](https://www.microsoft.com/en-us/download/details.aspx?id=30679)|
|msvcr120.dll<br />msvcp120.dll<br />mfc120.dll<br />mfc120u.dll<br />mfcmifc80.dll<br />mfcm120.dll<br />mfcm120u.dll<br />concrt120.dll<br />vccorlib120.dll<br />vcamp120.dll<br />vcomp120.dll|[Microsoft Visual C++ 2013 Redistributable (Links zu den einzelnen Downloads)](https://support.microsoft.com/en-us/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)<br />[Multibyte-MFC-Bibliothek für Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770)<br />[Visual C++ 2013 Runtime für Quergeladene Windows 8.1-apps (ZIP-Download)](http://download.microsoft.com/download/5/F/0/5F0F8404-9329-44A9-8176-ED6F7F746F25/VCLibs_Redist_Packages.zip)|
|vcruntime140.dll<br />vcruntime140_app.dll<br />msvcp140.dll<br />msvcp140_1.dll, etc.<br />mfc140.dll<br />mfc140u.dll<br />mfcmifc80.dll<br />mfcm140.dll<br />mfcm140u.dll<br />concrt140.dll<br />vccorlib140.dll<br />vcamp140.dll<br />vcomp140.dll|[Microsoft Visual C++ 2017 Redistributable (x86)](https://go.microsoft.com/fwlink/?LinkId=746571)<br />[Microsoft Visual C++ 2017 Redistributable (x64)](https://go.microsoft.com/fwlink/?LinkId=746572)|
|msvcr100_clr0400.dll<br />msvcr110_clr0400.dll<br />msvcr120_clr0400.dll|[.NET Framework herunterladen](https://www.microsoft.com/net/download/framework)|

### <a name="to-repair-an-existing-redistributable-package"></a>So reparieren Sie eine vorhandene Redistributable package

1. Öffnen Sie die Systemsteuerung. Geben Sie im Windows-10 *Systemsteuerung* in Desktop suchen Steuerelement auf der Taskleiste, und wählen Sie dann **Systemsteuerung** aus den Optionen.

2. Wählen Sie in der Systemsteuerung **Programme** > **Programme und Funktionen**. Wählen Sie die Version des verteilbaren Microsoft Visual C++, die die DLL entspricht, die nicht vorhanden ist. Wenn eine **Änderung** Schaltfläche am oberen Rand der Liste angezeigt wird, wählen Sie es. Ist die einzige Auswahlmöglichkeit **Deinstallieren**, Sie können diese Version des verteilbaren Pakets nicht reparieren.

3. Wählen Sie **Reparatur** in das Dialogfeld "Setup" für das verteilbare Paket. Sie müssen möglicherweise neu gestartet, wenn die Reparatur abgeschlossen ist.
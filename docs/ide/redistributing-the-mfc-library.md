---
title: Verteilen der MFC-Bibliothek | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca153ec9ca079bf13b1c1c1dcedd6e41497307f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="redistributing-the-mfc-library"></a>Verteilen der MFC-Bibliothek
Wenn Sie Ihre Anwendung mit der MFC-Bibliothek dynamisch verknüpfen, müssen Sie die entsprechende MFC-DLL verteilen. Wenn die MFC-app mit der Version von MFC, die geliefert wird mit Visual Studio 2015 erstellt wird, müssen Sie z. B. verteilen mfc140.dll oder mfc140u.dll, je nachdem, ob Ihre app für schmale Zeichen oder Unicode-Unterstützung kompiliert wird.  
  
> [!NOTE]
>  Die mfc140.dll Dateien wurden aus dem Verzeichnis verteilbaren Dateien in Visual Studio 2015 RTM ausgelassen. Sie können die Versionen von Visual Studio 2015 in den Verzeichnissen "Windows\System32" und Windows\syswow64 installiert werden, stattdessen verwenden.  
  
 Da alle MFC-DLLs die freigegebene Version der C-Laufzeitbibliothek (CRT) verwenden, müssen Sie möglicherweise auch die CRT zu verteilen. Die Version von MFC, die geliefert wird mit Visual Studio 2015 verwendet die universal CRT-Bibliothek, die als Teil von Windows 10 verteilt wird. Führen Sie eine MFC-Anwendung mit Visual Studio 2015 auf frühere Versionen von Windows erstellt haben, müssen Sie der Universal CRT verteilen. Informationen zum Verteilen von universal CRT als eine Komponente des Betriebssystems oder mithilfe einer lokalen Bereitstellung finden Sie unter [Einführung in die Universal CRT](http://go.microsoft.com/fwlink/p/?linkid=617977). Informationen zum Herunterladen der ausdrückt CRT für die zentrale Bereitstellung unter Windows unterstützten Versionen finden Sie unter [Windows 10 universelle C-Laufzeit](http://go.microsoft.com/fwlink/p/?LinkId=619489). Ucrtbase.dll für die lokale Bereitstellung verteilbare architekturspezifischer-Versionen befinden sich im Windows SDK. Standardmäßig installiert Visual Studio diese in C:\Program Files (x86) \Windows Kits\10\Redist\ucrt\DLLs\ in ein Unterverzeichnis architekturspezifischer.  
  
 Wenn Ihre app mit einer früheren Version der MFC-Bibliothek erstellt wird, müssen Sie die entsprechenden CRT-DLL aus dem Verzeichnis verteilbaren Dateien verteilen. Wenn die MFC-Anwendung mit dem Visual Studio 2013 (vc120)-Toolset erstellt wird, müssen Sie z. B. die msvcr120.dll verteilen. Außerdem müssen Sie die Mfc-Bibliothek übereinstimmende neu verteilen`<version>`u.dll oder Mfc`<version>`DLL.  
  
 Wenn Sie Ihre Anwendung mit MFC statisch verknüpfen (d. h., wenn Sie angeben, **MFC in einer statischen Bibliothek verwenden** auf die **allgemeine** Registerkarte der **Eigenschaftenseiten** Dialogfeld), Sie verfügen nicht über Um ein MFC-DLL weiterverteilen. Obwohl die statische Verknüpfung möglicherweise bei Tests und internen Bereitstellungen von Anwendungen funktioniert, sollte dieses Verfahren nicht zur Neuverteilung von MFC verwendet werden. Weitere Informationen zu den empfohlenen Vorgehensweisen für die Bereitstellung von Visual C++-Bibliotheken, finden Sie unter [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).  
  
 Wenn Ihre Anwendung die MFC-Klassen verwendet, die das WebBrowser-Steuerelement zu implementieren (z. B. [CHtmlView-Klasse](../mfc/reference/chtmlview-class.md) oder [CHtmlEditView Klasse](../mfc/reference/chtmleditview-class.md)), es wird empfohlen, dass Sie auch die aktuelle Version von installieren. Microsoft Internet Explorer so, dass der Zielcomputer aktuelle allgemeine Benutzersteuerelement-Dateien hat. (Dazu wird mindestens Internet Explorer 4.0 benötigt.) Informationen zur Installation von Internet Explorer-Komponenten finden Sie im Artikel 185375 zur Erstellung einer einzelnen EXE-Installation von Internet Explorer auf der Microsoft Support-Website.  
  
 Wenn Ihre Anwendung die MFC-Datenbankklassen verwendet (z. B. [CRecordset Klasse](../mfc/reference/crecordset-class.md) und [CRecordView-Klasse](../mfc/reference/crecordview-class.md)), müssen Sie ODBC und keine ODBC-Treiber von der Anwendung verwendeten verteilen. Weitere Informationen finden Sie unter [Neuverteilen von Datenbankunterstützungsdateien](../ide/redistributing-database-support-files.md).  
  
 Wenn die MFC-Anwendung Windows Forms-Steuerelemente verwendet, müssen Sie mfcmifc80.dll mit der Anwendung verteilen. Diese DLL ist eine starken Namen signiert, die mit einer Anwendung in den lokalen Ordner der Anwendung oder durch die Bereitstellung auf den globalen Assemblycache (GAC) mithilfe von verteilt werden, können die [Gacutil.exe (Global Assembly Cache-Tool)](/dotnet/framework/tools/gacutil-exe-gac-tool).  
  
 Wenn Sie eine MFC-DLL weiterverteilen, achten Sie darauf, nicht die Debugversion, sondern die Verkaufsversion weiterzuverteilen. Debugversionen der DLLs können nicht weiterverteilt werden. Die Namen der Debugversionen der MFC-DLLs enden mit "d", z. B. Mfc140d.dll.  
  
 Sie können MFC verteilen, indem Sie mit beiden VCRedist_*Architektur*.exe, Mergemodule, die mit Visual Studio oder durch Bereitstellen der MFC-DLL in denselben Ordner wie die Anwendung installiert sind. Weitere Informationen zur neuverteilung von MFC finden Sie unter [Neuverteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="installation-of-localized-mfc-components"></a>Installation lokalisierter MFC-Komponenten  
 Wenn Sie die Anwendung durch Installieren einer MFC-Lokalisierungs-DLL lokalisieren möchten, müssen Sie die verteilbaren Mergedateien (MSM-Datei) verwenden. Angenommen, wenn Sie die Anwendung auf x X86 zu lokalisieren möchten Computer, müssen Sie Microsoft_VC zusammenführen`<version>`_MFCLOC_x86.msm in das Installationspaket für x X86 Computer.  
  
 Die weiterverteilbaren MSM-Dateien enthalten die DLLs, die für die Lokalisierung verwendet werden. Es gibt eine DLL für jede unterstützte Sprache. Beim Installationsvorgang werden diese DLLs im Ordner "%WINDIR%\system32\" auf dem Zielcomputer installiert.  
  
 Weitere Informationen zum Lokalisieren von MFC-Anwendungen finden Sie unter [TN057: Lokalisierung von MFC-Komponenten](../mfc/tn057-localization-of-mfc-components.md), sowie [Artikel 208983: Verwenden von MFC LOC DLLs wie](http://go.microsoft.com/fwlink/p/?linkid=198025) auf der Microsoft-Support-Website.  
  
 Sie können MFC-Lokalisierungs-DLLs verteilen, indem Sie die MFC-DLL im lokalen Anwendungsordner bereitstellen. Weitere Informationen über das Verteilen von Visual C++-Bibliotheken finden Sie unter [Neuverteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verteilen von Visual C++-Dateien](../ide/redistributing-visual-cpp-files.md)
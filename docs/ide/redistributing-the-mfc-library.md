---
title: "Verteilen der MFC-Bibliothek"
ms.custom: na
ms.date: "12/14/2016"
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
  - "MFC, Verteilen"
  - "Verteilen der MFC-Bibliothek"
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
caps.latest.revision: 32
caps.handback.revision: "29"
ms.author: "corob"
manager: "ghogen"
---
# Verteilen der MFC-Bibliothek
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie die Anwendung dynamisch mit der MFC\-Bibliothek verknüpfen, müssen Sie die Datei "Msvcr100.dll" verteilen, da alle MFC\-DLLs die freigegebene Version der C\-Laufzeitbibliothek \(CRT\-Bibliothek\) verwenden.  Sie müssen auch "Mfc100u.dll" oder "Mfc100.dll" verteilen.  
  
 Wenn Sie die Anwendung statisch mit MFC verknüpfen, \(das heißt, wenn Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Allgemein** die Option **MFC in einer statischen Bibliothek verwenden** angeben\), müssen Sie die Datei "Mfc100u.dll" oder "Mfc100.dll" nicht neu verteilen.  Obwohl die statische Verknüpfung möglicherweise bei Tests und internen Bereitstellungen von Anwendungen funktioniert, sollte dieses Verfahren nicht zur Neuverteilung von MFC verwendet werden.  Weitere Informationen zu den empfohlenen Vorgehensweisen zum Bereitstellen von Visual C\+\+\-Bibliotheken finden Sie unter [Auswählen einer Bereitstellungsmethode](../ide/choosing-a-deployment-method.md).  
  
 Wenn die Anwendung die MFC\-Klassen verwendet, die das WebBrowser\-Steuerelement implementieren \(z. B. [CHtmlView\-Klasse](../mfc/reference/chtmlview-class.md) oder [CHtmlEditView Class](../mfc/reference/chtmleditview-class.md)\), sollte auch die aktuellste Version von Microsoft Internet Explorer installiert werden, damit auf dem Zielcomputer die aktuellen allgemeinen Steuerungsdateien vorhanden sind. \(Dazu wird mindestens Internet Explorer 4.0 benötigt.\) Informationen zur Installation von Internet Explorer\-Komponenten finden Sie im Artikel 185375 zur Erstellung einer einzelnen EXE\-Installation von Internet Explorer auf der Microsoft Support\-Website.  
  
 Wenn in der Anwendung die MFC\-Datenbankklassen \(z. B. [CRecordset Class](../mfc/reference/crecordset-class.md) und [CRecordView Class](../mfc/reference/crecordview-class.md)\) verwendet werden, müssen Sie ODBC und alle in der Anwendung verwendeten ODBC\-Treiber weiterverteilen.  Weitere Informationen finden Sie unter [Neuverteilen von Datenbankunterstützungsdateien](../ide/redistributing-database-support-files.md).  
  
 Wenn die MFC\-Anwendung Windows Forms\-Steuerelemente verwendet, müssen Sie mfcmifc80.dll mit der Anwendung verteilen.  Diese DLL ist eine mit einem starken Namen signierte .NET\-Assembly, die mit einer Anwendung in deren lokalem Ordner oder durch Bereitstellung im globalen Assemblycache \(GAC\) mit dem [Gacutil.exe \(Global Assembly Cache Tool\)](../Topic/Gacutil.exe%20\(Global%20Assembly%20Cache%20Tool\).md) verteilt werden kann.  
  
 Wenn Sie eine MFC\-DLL weiterverteilen, achten Sie darauf, nicht die Debugversion, sondern die Verkaufsversion weiterzuverteilen.  Debugversionen der DLLs können nicht weiterverteilt werden.  Die Namen von Debugversionen der MFC\-DLLs enden auf "d" enden, z. B. "Mfc100d.dll"  
  
 Wenn Sie in irgendeiner Weise MFC\-Quellen ändern und anschließend die MFC\-DLL neu erstellen, müssen Sie die geänderte MFC\-DLL umbenennen, um einen Konflikt mit der in Visual Studio enthaltenen MFC\-DLL zu vermeiden.  Es wird empfohlen, die MFC\-DLL nicht neu zu erstellen oder umzubenennen.  Weitere Informationen finden Sie unter MFC Technischer Hinweis 33.  
  
 Sie können MFC entweder mit VCRedist\_*architecture*.exe, Mergemodulen, die zusammen mit Visual Studio installiert werden, oder durch Bereitstellung der MFC\-DLL im gleichen Ordner wie die Anwendung weiterverteilen.  Weitere Informationen zur Weiterverteilung von MFC finden Sie unter [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
## Installation lokalisierter MFC\-Komponenten  
 Wenn Sie die Anwendung durch Installieren einer MFC\-Lokalisierungs\-DLL lokalisieren möchten, müssen Sie die verteilbaren Mergedateien \(MSM\-Datei\) verwenden.  Wenn Sie zum Beispiel die Anwendung auf einem x86\-Computer lokalisieren möchten, müssen Sie "Microsoft\_VC100\_MFCLOC\_x86.msm" im Installationspaket für einen x86\-Computer zusammenführen.  
  
 Die weiterverteilbaren MSM\-Dateien enthalten die DLLs, die für die Lokalisierung verwendet werden.  Es gibt eine DLL für jede unterstützte Sprache.  Beim Installationsvorgang werden diese DLLs im Ordner "%WINDIR%\\system32\\" auf dem Zielcomputer installiert.  
  
 Weitere Informationen zur Lokalisierung von MFC\-Anwendungen finden Sie unter [TN057: Lokalisierung von MFC\-Komponenten](../mfc/tn057-localization-of-mfc-components.md) sowie im [Artikel 208983 zum Verwenden von MFC LOC\-DLLs](http://go.microsoft.com/fwlink/?LinkId=198025) auf der Microsoft Support\-Website.  
  
 Sie können MFC\-Lokalisierungs\-DLLs verteilen, indem Sie die MFC\-DLL im lokalen Anwendungsordner bereitstellen.  Weitere Informationen zur Weiterverteilung von Visual C\+\+\-Bibliotheken finden Sie unter [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md).  
  
## Siehe auch  
 [Verteilen von Visual C\+\+\-Dateien](../ide/redistributing-visual-cpp-files.md)
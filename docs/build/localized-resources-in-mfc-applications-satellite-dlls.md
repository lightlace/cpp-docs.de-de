---
title: 'Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ba1c8d52796ae9251a79df9600be80612db33e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs
MFC-Version 7.0 und höher bietet erweiterte Unterstützung für Satelliten-DLLs, eine Funktion, die hilft beim Erstellen von Anwendungen, die für mehrere Sprachen lokalisiert. Eine Satelliten-DLL ist eine [reine Ressourcen-DLL](../build/creating-a-resource-only-dll.md) , enthält die Ressourcen einer Anwendung, die für eine bestimmte Sprache lokalisiert. Wenn die Anwendung mit der Ausführung beginnt, lädt MFC automatisch die lokalisierte Ressourcen für die Umgebung am besten geeignet. Sie konnten z. B. eine Anwendung mit der englischen Sprachressourcen mit zwei-Satelliten-DLLs, ein enthält eine französische Übersetzung der Ressourcen und die andere eine deutsche Übersetzung enthält haben. Wenn die Anwendung auf einem englischsprachigen System ausgeführt wird, wird die englischen Ressourcen verwendet. Wenn auf einem französischen System ausführen, verwendet es die französischen Ressourcen. Wenn auf einem deutschen System ausgeführt wird, wird die deutschen Ressourcen verwendet.  
  
 In einer bestimmten Sprache lokalisiert, die Ressourcen enthalten, zur Unterstützung von lokalisierter Ressourcen in einer MFC-Anwendung MFC versucht, eine Satelliten-DLL zu laden. Satelliten-DLLs werden mit dem Namen *AnwendungsnameXXX*DLL-Datei, in denen *Parameter "ApplicationName"* ist der Name der .exe oder .dll verwenden von MFC, und *XXX* ist der drei Buchstaben bestehenden Code für die Sprache die Ressourcen (z. B. "ENU" oder "DEU").  
  
 MFC versucht, laden die Ressourcen-DLL für jede der folgenden Sprachen in der Reihenfolge und hört auf, wenn ein solches gefunden:  
  
1.  (Nur Windows 2000 oder höher) Standardmäßige Benutzeroberflächensprache des aktuellen Benutzers, von der Win32-API GetUserDefaultUILanguage() zurückgegeben.  
  
2.  (Nur Windows 2000 oder höher) Der aktuelle Benutzer standardmäßig Benutzeroberflächensprache ohne eine bestimmte Sprachvariante an (d. h. ENC [Kanadische Englisch] wird ENU [USA Englisch]).  
  
3.  Standard-Benutzeroberflächensprache des Systems. Unter Windows 2000 oder höher, ist dies die GetSystemDefaultUILanguage()-API zurückgegeben. Auf anderen Plattformen ist dies die Sprache des Betriebssystems selbst.  
  
4.  Das System standardmäßig Benutzeroberflächensprache, ohne eine bestimmte Sprachvariante an.  
  
5.  Eine gefälschte Sprache mit 3 Buchstaben bestehenden Code "loc" abgerufen  
  
 Wenn MFC Satelliten-DLLs nicht findet, verwendet sie Ressourcen in der Anwendung selbst enthalten sind.  
  
 Nehmen wir beispielsweise an, dass eine Anwendung LangExample.exe MFC verwendet und mehrere Benutzeroberflächen-System auf einem Windows 2000 ausgeführt wird; die Benutzeroberflächensprache des Systems ist ENU [USA Englisch] und Benutzeroberflächensprache des aktuellen Benutzers auf FRC [Französisch (Kanada)] festgelegt ist. MFC sucht die folgenden DLLs in der folgenden Reihenfolge aus:  
  
1.  SprachenbeispielFRC.dll (Benutzeroberflächensprache des Benutzers).  
  
2.  LangExampleFRA.dll (Benutzeroberflächensprache des Benutzers ohne Sprachvariante, in diesem Beispiel wird Französisch (Frankreich).  
  
3.  SprachenbeispielENU.dll (Benutzeroberflächensprache des Systems).  
  
4.  LangExampleLOC.dll.  
  
 Wenn keine dieser DLLs gefunden werden, verwendet MFC die Ressourcen in LangExample.exe an.  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)   
 [TN057: Lokalisierung von MFC-Komponenten](../mfc/tn057-localization-of-mfc-components.md)
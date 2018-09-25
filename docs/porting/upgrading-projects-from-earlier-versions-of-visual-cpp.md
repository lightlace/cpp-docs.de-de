---
title: Aktualisieren von Projekten von früheren Versionen von Visual C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 32-bit code porting
- upgrading Visual C++ applications, 32-bit code
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8091bbba7dcee344677c54a7944708679f2ff867
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411845"
---
# <a name="upgrading-projects-from-earlier-versions-of-visual-c"></a>Aktualisieren von Projekten von früheren Versionen von Visual C++

In den meisten Fällen können Sie ein Projekt öffnen, das in einer früheren Version von Visual Studio erstellt wurde. Damit dies jedoch möglich ist, aktualisiert Visual Studio das Projekt. Wenn Sie dieses aktualisierte Projekt speichern, kann es nicht in der früheren Version geöffnet werden.  
  
> [!IMPORTANT]
> Wenn Sie versuchen, ein Projekt zu konvertieren, das bereits konvertiert war, fordert Visual Studio eine Bestätigung an, da bei der erneuten Konvertierung vorhandene Dateien gelöscht werden.  
  
Viele aktualisierte Projekte und Projektmappen können ohne Änderung erfolgreich erstellt werden. Einige Projekte erfordern möglicherweise Änderungen bei den Einstellungen, bei der Quelle oder bei beidem. Es wird empfohlen, dass Sie anhand der folgenden Richtlinien zuerst die Einstellungsprobleme behandeln. Wenn das Projekt dann immer noch nicht erstellt werden kann, können Sie die Codeprobleme behandeln. Weitere Informationen finden Sie in der [Übersicht über potenzielle Probleme beim Upgrade](../porting/overview-of-potential-upgrade-issues-visual-cpp.md).  
  
1. Erstellen Sie eine Kopie der vorhandenen Projekt- und Projektmappendateien. Installieren Sie die aktuelle Version von Visual Studio und parallel dazu die frühere Version, sodass Sie die Versionen der Dateien vergleichen können, wenn Sie dies möchten.  
  
2. Öffnen Sie – und aktualisieren Sie somit – in der aktuellen Version von Visual Studio die Kopie des Projekts oder der Projektmappe, und speichern Sie diese dann.  
  
3. Öffnen Sie für jedes konvertierte Projekt das Kontextmenü, und wählen Sie **Eigenschaften**aus. Wählen Sie unter **Konfigurationseigenschaften**die Option **Allgemein** aus, und wählen Sie dann für **Plattformtoolset**die aktuelle Version. (Für Visual Studio 2017 wählen Sie beispielsweise **v141** aus.)  
  
4. Erstellen Sie die Projektmappe. Wenn die Erstellung nicht erfolgen kann, ändern Sie die Einstellungen oder führen Sie die Erstellung erneut durch.  
  
Datenquellen sind in einem getrennten Datenbankprojekt enthalten, sodass Sie die gespeicherten Prozeduren in diesen Quellen einfacher ändern und debuggen können. Wenn Sie ein C++-Projekt aktualisieren, das Datenquellen enthält, wird automatisch ein getrenntes Datenbankprojekt erstellt.  
  
Weitere Informationen zum Aktualisieren der entsprechenden Windows-Versionen finden Sie unter [Ändern von WINVER und _WIN32_WINNT](../porting/modifying-winver-and-win32-winnt.md).  
  
## <a name="see-also"></a>Siehe auch  

[Buildsystemänderungen](../build/build-system-changes.md)<br/>
[Neues bei Visual C++ in Visual Studio 2017](../what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
[Änderungsverlauf von Visual C++ von 2003 bis 2015](../porting/visual-cpp-change-history-2003-2015.md)<br/>
[Nicht dem Standard entsprechendes Verhalten](../cpp/nonstandard-behavior.md)
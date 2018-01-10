---
title: "Benennungskonventionen für Bibliothek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NAFXCW.LIB [MFC]
- libraries [MFC], static
- coding conventions [MFC], MFC library names
- NAFXCWD.LIB [MFC]
- console applications [MFC], MFC library versions
- naming conventions [MFC], MFC object code libraries
- object code libraries, MFC naming conventions
- object code libraries
- conventions [MFC], MFC library names
- MFC libraries, naming conventions
ms.assetid: 39fe7d93-5a14-4c6a-b16c-bf318fa01278
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14e217b3cfd9f3618046cf1a0ca825eb2e6492f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="library-naming-conventions"></a>Bibliotheks-Benennungskonventionen
Objektcodebibliotheken für MFC-verwenden Sie die folgenden Benennungskonventionen. Die Bibliotheksnamen haben das Format  
  
 *u*AFX*c*W*d*. LIB  
  
 die Buchstaben kursiv dargestellten Kleinbuchstaben Platzhalter für Bezeichner gegangenem, dessen Bedeutung in der folgenden Tabelle angezeigt werden:  
  
### <a name="library-naming-conventions"></a>Bibliotheks-Benennungskonventionen  
  
|Bezeichner|Werte und Bedeutung|  
|---------------|-------------------------|  
|*u*|ANSI (N) oder Unicode (U)|  
|*c*|Typ des zu erstellenden Programms: C = all|  
|*d*|Debug- oder Release: D = Debug; Spezifizierer für Version auslassen|  
  
 Standardmäßig werden Windows-Anwendung für die Intel Plattform Debugbuild: NAFXCWD.Lib. Alle Bibliotheken, die in der folgenden Tabelle aufgeführt sind, enthalten im Verzeichnis \atlmfc\lib vorgefertigten.  
  
### <a name="static-link-library-naming-conventions"></a>Static Link Library-Benennungskonventionen  
  
|Bibliothek|Beschreibung|  
|-------------|-----------------|  
|NAFXCW.LIB|MFC-Static Link Library, Originalversion|  
|NAFXCWD.LIB|MFC-Static Link Library Debugversion|  
|UAFXCW.LIB|MFC-Static Link Library mit Unicode-Unterstützung, Releaseversion|  
|UAFXCWD.LIB|Static Link Library mit Unicode-Unterstützung, die Debugversion von MFC|  
  
> [!NOTE]
>  Wenn Sie eine Bibliotheksversion erstellen möchten, finden Sie in der Datei "Readme.txt" im Verzeichnis \atlmfc\src\mfc. Diese Datei wird beschrieben, verwenden das mitgelieferte Makefile mit NMAKE.  
  
 Weitere Informationen finden Sie unter [Namenskonventionen für MFC-DLLs](../build/naming-conventions-for-mfc-dlls.md) und [Unicode-Versionen der MFC-Bibliotheken](../mfc/unicode-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Bibliotheksversionen](../mfc/mfc-library-versions.md)


---
title: Allgemeine Klassenentwurf | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b2d0915c4b2940e93b781e7a56e2640c64a7f20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="general-class-design-philosophy"></a>Allgemeine Prinzipien für den Klassenentwurf
Microsoft Windows wurde entwickelt, lange vor die Programmiersprache C++ beliebten wurde. Da Sie Tausende von Anwendungen die Programmiersprache C-Windows-Anwendungsprogrammierschnittstelle (API) verwenden, wird diese Schnittstelle für absehbare verwaltet werden. Alle C++-Windows-Benutzeroberfläche muss daher auf den prozeduralen C-Sprachen-API erstellt werden. Damit wird sichergestellt, dass C++-Anwendungen mit C-Programme koexistieren können.  
  
 Die Microsoft Foundation Class-Bibliothek ist eine objektorientierte Schnittstelle für Fenster, in denen die folgenden Entwurfsziele erfüllt:  
  
-   Deutlich reduziert den Aufwand beim Schreiben einer Anwendung für Windows.  
  
-   Die ausführungsgeschwindigkeit ist vergleichbar mit der C-Sprachen-API.  
  
-   Minimale Größe Aufwand.  
  
-   Die Möglichkeit, alle Windows-C-Funktion direkt aufzurufen.  
  
-   Einfacher Konvertierung von vorhandenen C-Anwendungen in C++.  
  
-   Die Fähigkeit, von der vorhandenen Basisklasse der Programmiersprache C Windows-Programmierung zu nutzen.  
  
-   Leichtere Verwendung der Windows-API mit C++ als mit C.  
  
-   Einfacher verwenden dennoch leistungsfähige Abstraktionen von komplizierter Funktionen, z. B. ActiveX-Steuerelemente, datenbankunterstützung, drucken, Symbolleisten und Statusleisten.  
  
-   "True" Windows-API für C++, die effektiv die Funktionen der Programmiersprache C++ verwendet.  
  
 Weitere Informationen über den Entwurf der MFC-Bibliothek finden Sie unter:  
  
-   [Das Anwendungsframework](../mfc/application-framework.md)  
  
-   [Beziehung zum C-Sprachen-API](../mfc/relationship-to-the-c-language-api.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)


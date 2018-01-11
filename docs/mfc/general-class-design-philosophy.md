---
title: Allgemeine Klassenentwurf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c174b06b27e78ca61d2608b8e04205068ac436e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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


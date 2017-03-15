---
title: "Klassen f&#252;r einfache Datentypen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datenklassen [C++]"
  - "Skalarklassen [C++]"
  - "Klassen für einfache Datentypen"
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Klassen f&#252;r einfache Datentypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Klassen kapseln Zeichnungskoordinaten, Zeichenfolgen und Uhrzeit und Datumsinformationen und ermöglichen einfachen Verwendung der C\+\+\-Syntax.  Diese Objekte werden weiter als Parameter an den Memberfunktionen von Windows\-Klassen in der Klassenbibliothek verwendet.  Da `CPoint`, `CSize` und `CRect` in **PUNKT**, **GRÖSSE** und `RECT`\-Strukturen in [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] jeweils entsprechen, können Sie Objekte dieser C\+\+\-Klassen verwenden, wo Sie diese Sprache C Strukturen verwenden können.  Die Klassen stellen nützliche Schnittstellen durch deren Memberfunktionen bereit.  `CStringT` stellt sehr flexible dynamische Zeichenfolgen.  `CTime`, `COleDateTime`, `CTimeSpan` und **COleTimeSpan** vornehmen Zeit und Datumswerte dar.  Weitere Informationen über diese Klassen, finden Sie im Artikel [Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md).  
  
 Klassen, die mit "**COle**" beginnen, sind Kapselungen aus den Datentypen, die in OLE bereitgestellt werden.  Diese Datentypen können in den Windows\-Programmen unabhängig davon verwendet werden, ob andere OLE\-Funktionen verwendet werden.  
  
 [CStringT\-Klasse](../atl-mfc-shared/reference/cstringt-class.md)  
 Hält Zeichenfolgen an.  
  
 [CTime](../atl-mfc-shared/reference/ctime-class.md)  
 Threads absoluten Zeit und Datumswerte.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper für den OLE\-Automatisierungs\-Typ **DATUM**.  Stellt Datums\- und Uhrzeitwerte dar.  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 als relative Zeit und Datumswerte.  
  
 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)  
 Hält Verwandt `COleDateTime`\-Werte, z der Unterschied zwischen zwei `COleDateTime`\-Werte an.  
  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Threads koordinieren \(x, y\) von Paaren.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Threads überholen, oder relativen Positionen bei zugeordneten Werte.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Griffkoordinaten rechteckigen von Bereichen.  
  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Stellt die Funktionalität der Windows\-Image\-Liste bereit.  Grafiklisten werden mit Strukturansicht\-Steuerelementen Listen\-Steuerelementen und verwendet.  Sie können auch verwendet werden, um einen Satz gleich\-skalierte Bitmaps zu speichern und zu archivieren.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper für den OLE\-Automatisierungs\-Typ **VARIANT**.  Daten in **VARIANT**s können in vielen Formaten gespeichert werden.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper für den OLE\-Automatisierungs\-Typ **WÄHRUNG**, ein arithmetischer Typ des Festkommas, mit 15 Ziffern vor dem Dezimaltrennzeichen und 4 Ziffern nach.  
  
> [!NOTE]
>  Ab Visual C\+\+ .NET, sind `CRect`, `CSize` und `CPoint` geändert, um entweder in ATL oder in MFC\-Anwendungen verwendbar sein.  Darüber hinaus ist `CStringT` hinzugefügt, um eine MFC\-unabhängige ähnliche Klasse `CString` bereitzustellen.  Weitere Informationen über freigegebene Hilfsklassen, finden Sie unter [Freigegebene Klassen](../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)
---
title: "Klassen f&#252;r Dokumentvorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.document"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dokumentvorlagen, Klassen"
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Klassen f&#252;r Dokumentvorlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dokumentvorlagenobjekte koordinieren die Dokumentenerstellung, zeigen und Rahmenfensterobjekte an, wenn ein neues Dokument oder eine Ansicht erstellt wird.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)  
 Die Basisklasse für Dokumentvorlagen.  Sie verwenden nie diese Klasse direkt; Stattdessen verwenden Sie eine der anderen Dokumentvorlagenklassen, die von dieser Klasse abgeleitet werden.  
  
 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)  
 Eine Vorlage für Dokumente in mehrfachen Dokumentschnittstelle \(MDI\).  MDI\-Anwendungen können mehrere Dokumente gleichzeitig, die geöffnet sind.  
  
 [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)  
 Eine Vorlage für Dokumente im \(Single Document Interface \(SDI\).  SDI\-Anwendungen haben nur ein Dokument, das gleichzeitig geöffnet ist.  
  
## Verwandte Klasse  
 [CCreateContext](../mfc/reference/ccreatecontext-structure.md)  
 Eine Struktur wurde durch eine Normal\-Vorlage zu den FensterErstellungsfunktionen, um die Dokumentenerstellung, Ansicht und Rahmenfensterobjekte zu koordinieren.  
  
## Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)
---
title: "Serialisierung: Serialisieren eines Objekts"
ms.custom: na
ms.date: "12/03/2016"
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
  - "Objekte [C++], Serialisieren"
  - "Serialisierung [C++], Objekte"
  - "Serialisieren von Objekten [C++]"
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Serialisierung: Serialisieren eines Objekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Artikel [Serialisierung: Direkter eine serialisierbare Klasse](../mfc/serialization-making-a-serializable-class.md) zeigt, wie eine Klasse serialisierbar macht.  Sobald eine serialisierbare Klasse haben, können Sie Objekte dieser Klasse in und aus einer Datei zu einem [CArchive](../mfc/reference/carchive-class.md)\-Objekt serialisieren.  Dieser Artikel beschreibt:  
  
-   [Ein der für CArchive\-Objekt ist](../mfc/what-is-a-carchive-object.md).  
  
-   [Zwei Möglichkeiten, ein CArchive zu erstellen](../mfc/two-ways-to-create-a-carchive-object.md).  
  
-   [Verwenden des CArchive verwendet \<\< und \>\>\-Operatoren](../mfc/using-the-carchive-output-and-input-operators.md).  
  
-   [CObjects zu einem Archiv Speichern und Laden](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Sie können das Framework das Archiv für das serialisierbares Dokument erstellen oder das `CArchive`\-Objekt explizit erstellen lassen sich.  Sie können Daten zwischen einer Datei und einem serialisierbaren Objekt, indem Sie verwenden \<\< und \>\>\-Operatoren für `CArchive` oder in einigen Fällen indem Sie die `Serialize`\-Funktion von `CObject` abgeleitete Klasse aufrufen.  
  
## Siehe auch  
 [Serialisierung](../mfc/serialization-in-mfc.md)
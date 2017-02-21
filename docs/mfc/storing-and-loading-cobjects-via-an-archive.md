---
title: "Speichern und Laden eines CObject per Archiv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive-Klasse, Speichern und Laden von Objekten"
  - "CObject-Klasse, CArchive-Objekte"
  - "CObjects"
  - "CObjects, Laden durch Archive"
  - "Serialize-Methode, kontra CArchive-Operatoren"
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Speichern und Laden eines CObject per Archiv
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Speichern und Laden von `CObject`s zu einem Archiv erfordert zusätzliche Überlegung.  In bestimmten Fällen sollten Sie die `Serialize`\-Funktion des Objekts aufrufen, in dem das `CArchive`\-Objekt ein Parameter des `Serialize` \- Aufrufs, im Gegensatz zur Verwendung des **\<\<** oder **\>\>**\-Operators `CArchive`.  Der Tatsache wichtige erkennen ist, dass der Operator `CArchive``CObject`**\>\>** im Arbeitsspeicher auf `CRuntimeClass` basieren Informationen erstellt, die dem der Datei durch das Archiv speichernde geschrieben werden.  
  
 Daher ob Sie `CArchive` mit **\<\<** und **\>\>**, Operatoren für das Aufrufen von `Serialize`, hängt davon ab, ob Sie das Ladenarchiv *benötigen*, um das Objekt auf Grundlage zuvor gespeicherte `CRuntimeClass` Informationen dynamisch zu rekonstruieren.  Verwenden Sie die Funktion `Serialize` in den folgenden Fällen:  
  
-   Wenn Sie das Objekt deserialisieren, kennen Sie die exakte Klasse des Objekts zuvor.  
  
-   Wenn Sie das Objekt deserialisieren, verfügen Sie bereits den Arbeitsspeicher, der dafür zugeordnet ist.  
  
> [!CAUTION]
>  Wenn Sie das Objekt mit der `Serialize`\-Funktion geladen, müssen Sie das Objekt mit der `Serialize`\-Funktion auch speichern.  Speichern Sie nicht mit dem Operator `CArchive` **\<\<** und laden dann mit der `Serialize`\-Funktion oder der Speicher mit der `Serialize`\-Funktion und laden dann mit Operators **CArchive \>\>**.  
  
 Das folgende Beispiel veranschaulicht die Fälle:  
  
 [!CODE [NVC_MFCSerialization#36](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#36)]  
  
 [!CODE [NVC_MFCSerialization#37](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSerialization#37)]  
  
 Zusammenfassend wenn die Klasse **CObjec** serialisierbare eingebettetes t als Member definiert, sollte `CArchive` **\<\<** und **\>\>** für Operatoren dieses Objekt *nicht* verwenden, sondern sollten die `Serialize` stattdessen Funktion aufrufen.  Wenn Ihre serialisierbare Klasse einen Zeiger auf `CObject` \(oder einem Objekt wird von `CObject` abgeleitet\) als Member definiert, erstellt jedoch dieses anderen Objekt im eigenen Konstruktor, sollten Sie `Serialize` aufrufen.  
  
## Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)
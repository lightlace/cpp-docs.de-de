---
title: "CColumnAccessor-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CColumnAccessor"
  - "ATL::CColumnAccessor"
  - "ATL.CColumnAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CColumnAccessor-Klasse"
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CColumnAccessor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generiert Zusammenfassungstabelle Consumercode ein.  
  
## Syntax  
  
```  
class CColumnAccessor : public CAccessorBase  
```  
  
## Hinweise  
 Im eingefügten Code wird jede Spalte als separater Accessor gebunden.  Sie sollten beachten, dass diese Klasse im eingefügten Code \(beispielsweise, können Sie ihn an, als Debuggen\), verwendet werden, aber Sie müssen ihn oder seine Methoden in der Regel nie direkt verwenden.  
  
 `CColumnAccessor` implementiert die folgenden Stubmethoden, von denen jede der Funktionen zu anderen Accessorklassenmethoden entsprechen:  
  
-   `CColumnAccessor`; der Konstruktor instanziiert und initialisiert das `CColumnAccessor`\-Objekt.  
  
-   `CreateAccessor` belegt für die Bindung Strukturen der Spalte Speicher und initialisiert die Spaltendatenmembern.  
  
-   **BindColumns** ausführen zu den Accessoren.  
  
-   **SetParameterBuffer** ordnet Puffern für Parameter zu.  
  
-   `AddParameter` fügt ein Parametereintrag den Parametereintragsstrukturen hinzu.  
  
-   **HasOutputColumns** legt fest, ob der Accessor Ausgabespalten hat  
  
-   **HasParameters** legt fest, ob der Accessor Parameter verfügt.  
  
-   `BindParameters` umschließt die erstellten Parameter an Spalten.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)
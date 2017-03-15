---
title: "Bin&#228;re Operatoren | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Binäre Operatoren"
  - "Memberauswahloperatoren"
  - "Operatoren [C++], Binär"
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Bin&#228;re Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgende Tabelle zeigt eine Liste von Operatoren, die überladen werden können.  
  
### Neu definierbare binäre Operatoren  
  
|Operator|Name|  
|--------------|----------|  
|**,**|Komma|  
|`!=`|Ungleichheit|  
|`%`|Modulooperator|  
|`%=`|Modulo\/Zuweisung|  
|**&**|Bitweises AND|  
|**&&**|Logisches AND|  
|**&\=**|Bitweises AND\/Zuweisung|  
|**\***|Multiplikation|  
|**\*\=**|Multiplikation\/Zuweisung|  
|**\+**|Addition|  
|`+=`|Addition\/Zuweisung|  
|**–**|Subtraktion|  
|**–\=**|Subtraktion\/Zuweisung|  
|**–\>**|Memberauswahl|  
|**–\>\***|Pointer\-to\-member\-Auswahl|  
|**\/**|Division|  
|`/=`|Division\/Zuweisung|  
|**\<**|Kleiner als|  
|**\<\<**|Nach links verschieben|  
|**\<\<\=**|Nach links verschieben\/Zuweisung|  
|**\<\=**|Kleiner oder gleich|  
|**\=**|Zuweisung|  
|`==`|Gleichheit|  
|**\>**|Größer als|  
|**\>\=**|Größer oder gleich|  
|**\>\>**|Nach rechts verschieben|  
|**\>\>\=**|Nach rechts verschieben\/Zuweisung|  
|**^**|Exklusives OR|  
|`^=`|Exklusives OR\/Zuweisung|  
|**&#124;**|Bitweises inklusives OR|  
|`&#124;=`|Bitweises inklusives OR\/Zuweisung|  
|`&#124;&#124;`|Logisches OR|  
  
 Um eine binäre Operatorfunktion als nicht statischen Member zu deklarieren, muss sie im folgenden Format deklariert werden:  
  
 *ret\-type* **operator**`op`**\(** `arg` **\)**  
  
 Dabei ist *ret\-type* der Rückgabetyp, `op` ist einer der in der vorhergehenden Tabelle aufgelisteten Operatoren und `arg` ist ein Argument eines beliebigen Typs.  
  
 Um eine binäre Operatorfunktion als globale Funktion zu deklarieren, muss sie im folgenden Format deklariert werden:  
  
 *ret\-type* **operator**`op`**\(** `arg1`**,** `arg2` **\)**  
  
 Dabei entsprechen *ret\-type* und `op` der Beschreibung für Memberoperatorfunktionen und `arg1` sowie `arg2` sind Argumente.  Mindestens eines der Argumente muss ein Klassentyp sein.  
  
> [!NOTE]
>  Es gibt keine Einschränkung für die Rückgabetypen der binären Operatoren. Die meisten benutzerdefinierten binären Operatoren geben jedoch entweder einen Klassentyp oder einen Verweis auf einen Klassentyp zurück.  
  
## Siehe auch  
 [Überladen von Operatoren](../cpp/operator-overloading.md)
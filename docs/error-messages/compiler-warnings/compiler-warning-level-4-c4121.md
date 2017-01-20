---
title: "Compiler Warning (level 4) C4121"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4121"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4121"
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Warning (level 4) C4121
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': Ausrichtung eines Elements hängt vom Pragma 'pack' ab  
  
 Der Compiler hat eine Auffüllung hinzugefügt, um einen Strukturmember an der Ausrichtungsgrenze auszurichten, aber der Paketwert ist geringer als die Größe des Members.  Beispielsweise wird durch folgenden Codeausschnitt C4121 erstellt:  
  
```  
// C4121.cpp  
// compile with: /W4 /c  
#pragma pack(2)  
struct s  
{  
   char a;  
   int b; // C4121  
   long long c;  
};  
```  
  
 Nehmen Sie zur Behebung dieses Problems eine der folgenden Änderungen vor:  
  
-   Ändern Sie die Paketgröße mindestens auf die Größe des Members, der die Warnung verursacht hat.  Ändern Sie beispielsweise in diesem Ausschnitt `pack(2)` in `pack(4)` oder `pack(8)`.  
  
-   Ordnen Sie die Memberdeklarationen aufsteigend nach Größe neu an.  Kehren Sie im Codeausschnitt die Reihenfolge der Strukturmember um, sodass der Member `long long` vor `int` und der Member `int` vor `char` platziert ist.  
  
 Diese Warnung tritt nur auf, wenn der Compiler den Datenmembern eine Auffüllung voranstellt.  Sie tritt nicht auf, wenn beim Packen Daten an einer Speicheradresse platziert werden, die für den Datentyp nicht ausgerichtet ist, aber dem Datenmember keine Auffüllung vorangestellt wurde.  Daten, die nicht an Grenzen ausgerichtet sind, bei denen es sich um ein Vielfaches der Datengröße handelt, können die Leistung mindern.  Lese\- und Schreibvorgänge von nicht ausgerichteten Daten führen in manchen Architekturen zu Prozessorfehlern; die Behebung dieser Fehler nimmt zwei\- bis dreimal mehr Zeit in Anspruch.  Zugriffe auf nicht ausgerichtete Daten können zu einigen RISC\-Architekturen nicht portiert werden.  
  
 Sie können zur Angabe der Strukturausrichtung [\#pragma pack](../../preprocessor/pack.md) oder [\/Zp](../../build/reference/zp-struct-member-alignment.md) verwenden. \(Bei Angabe von **\/Zp1** generiert der Compiler diese Warnung nicht.\)
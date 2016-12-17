---
title: "C-Kommentare"
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
  - "C"
helpviewer_keywords: 
  - "/* */-Kommentartrennzeichen"
  - "Codekommentare, C-Code"
  - "Kommentare"
  - "Kommentare, C-Code"
  - "Kommentare, Dokumentierender Code"
ms.assetid: 0f5f2825-e673-49e7-8669-94e2f5294989
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# C-Kommentare
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein "Kommentar" ist eine Folge von Zeichen, die mit einer Kombination aus Schrägstrich und Sternchen \(**\/\***\)beginnt, und vom Compiler als einzelnes Leerzeichen behandelt und andernfalls ignoriert wird.  Ein Kommentar kann jede Kombination von Zeichen aus dem darstellbaren Zeichensatz enthalten, einschließlich Zeilenumbruchzeichen, aber ausschließlich des "Kommentarende"\-Trennzeichens \(**\*\/**\).  Kommentare können mehr als eine Zeile belegen, jedoch nicht geschachtelt werden.  
  
 Kommentare können an beliebiger Stelle angezeigt werden, wo ein Leerzeichen gestattet ist.  Da der Compiler einen Kommentar als einzelnes Leerzeichen behandelt, können Sie Kommentare nicht in Token einschließen.  Der Compiler ignoriert die Zeichen im Kommentar.  
  
 Verwenden Sie Kommentare, um den Code zu dokumentieren.  Dieses Beispiel zeigt einen Kommentar, der vom Compiler akzeptiert wird:  
  
```  
/* Comments can contain keywords such as  
   for and while without generating errors. */  
```  
  
 Kommentare können in derselben Zeile wie eine Codeanweisung angezeigt werden:  
  
```  
printf( "Hello\n" );  /* Comments can go here */  
```  
  
 Sie können Funktionen oder Programmmodulen einen aussagekräftigen Kommentarblock voranstellen:  
  
```  
/* MATHERR.C illustrates writing an error routine   
 * for math functions.   
 */   
```  
  
 Da Kommentare keine geschachtelten Kommentare enthalten können, verursacht dieses Beispiel einen Fehler:  
  
```  
/* Comment out this routine for testing   
  
   /* Open file */  
    fh = _open( "myfile.c", _O_RDONLY );  
    .  
    .  
    .  
 */  
```  
  
 Der Fehler tritt auf, weil der Compiler das erste `*/` nach den Wörtern `Open file` als Ende des Kommentars erkennt.  Es versucht, den restlichen Text zu verarbeiten, und erzeugt einen Fehler, wenn es das `*/` außerhalb eines Kommentars findet.  
  
 Sie können zwar Kommentare verwenden, um bestimmte Codezeilen zu Testzwecken als inaktiv zu rendern, die Präprozessordirektiven `#if` und `#endif` sowie die bedingte Kompilierung sind jedoch nützliche Alternativen für diese Aufgabe.  Weitere Informationen finden Sie unter [Präprozessordirektiven](../preprocessor/preprocessor-directives.md) in der *Präprozessorreferenz*.  
  
 **Microsoft\-spezifisch**  
  
 Der Microsoft\-Compiler unterstützt ebenfalls einzeilige Kommentare, denen zwei Schrägstriche \(**\/\/**\) vorangestellt wurden.  Wenn Sie mit \/Za \(ANSI\-Standard\) kompilieren, generieren diese Kommentare Fehler.  Diese Kommentare dürfen nicht auf eine zweite Zeile erweitert werden.  
  
```  
// This is a valid comment  
```  
  
 Kommentare, die mit zwei Schrägstrichen \(**\/\/**\) beginnen, werden durch das nächste Zeilenumbruchzeichen, dem kein Escapezeichen vorangestellt ist, beendet.  Im folgenden Beispiel wird dem Zeilenumbruchzeichen ein umgekehrter Schrägstrich \(**\\**\) vorangestellt, wodurch eine "Escapesequenz" erstellt wird. Diese Escapesequenz bewirkt, dass der Compiler die nächste Zeile als Teil der vorherigen Zeile behandelt. \(Weitere Informationen finden Sie unter [Escapesequenzen](../c-language/escape-sequences.md).\)  
  
```  
// my comment \  
    i++;   
```  
  
 Daher wird die `i++;`\-Anweisung auskommentiert.  
  
 Bei Microsoft C sind die Microsoft\-Erweiterungen standardmäßig aktiviert.  Verwenden Sie \/Za, um diese Erweiterungen zu deaktivieren.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Tokens](../c-language/c-tokens.md)
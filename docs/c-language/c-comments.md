---
title: C-Kommentare | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C code
- comments, documenting code
- comments, C code
- /* */ comment delimiters
- comments
ms.assetid: 0f5f2825-e673-49e7-8669-94e2f5294989
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2eccff8ab582270f766fdbcb448fdb91145e348
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121743"
---
# <a name="c-comments"></a>C-Kommentare
Ein „Kommentar“ ist eine Folge von Zeichen, die mit einer Kombination aus Schrägstrich und Sternchen (<b>/\*</b>)beginnt und vom Compiler als einzelnes Leerzeichen behandelt und andernfalls ignoriert wird. Ein Kommentar kann jede Kombination von Zeichen aus dem darstellbaren Zeichensatz enthalten, einschließlich Zeilenumbruchzeichen, aber ausschließlich des „Kommentarende“-Trennzeichens (<b>\*/</b>). Kommentare können mehr als eine Zeile belegen, jedoch nicht geschachtelt werden.  
  
 Kommentare können an beliebiger Stelle angezeigt werden, wo ein Leerzeichen gestattet ist. Da der Compiler einen Kommentar als einzelnes Leerzeichen behandelt, können Sie Kommentare nicht in Token einschließen. Der Compiler ignoriert die Zeichen im Kommentar.  
  
 Verwenden Sie Kommentare, um den Code zu dokumentieren. Dieses Beispiel zeigt einen Kommentar, der vom Compiler akzeptiert wird:  
  
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
  
 Der Fehler tritt auf, weil der Compiler das erste `*/` nach den Wörtern `Open file` als Ende des Kommentars erkennt. Es versucht, den restlichen Text zu verarbeiten, und erzeugt einen Fehler, wenn es das `*/` außerhalb eines Kommentars findet.  
  
 Sie können zwar Kommentare verwenden, um bestimmte Codezeilen zu Testzwecken als inaktiv zu rendern, die Präprozessordirektiven `#if` und `#endif` sowie die bedingte Kompilierung sind jedoch nützliche Alternativen für diese Aufgabe. Weitere Informationen finden Sie unter [Präprozessordirektiven](../preprocessor/preprocessor-directives.md) in der *Präprozessorreferenz*.  
  
 **Microsoft-spezifisch**  
  
 Der Microsoft-Compiler unterstützt ebenfalls einzeilige Kommentare, denen zwei Schrägstriche (__//__) vorangestellt wurden. Wenn Sie mit /Za (ANSI-Standard) kompilieren, generieren diese Kommentare Fehler. Diese Kommentare dürfen nicht auf eine zweite Zeile erweitert werden.  
  
```  
// This is a valid comment  
```  
  
 Kommentare, die mit zwei Schrägstrichen (__//__) beginnen, werden durch das nächste Zeilenumbruchzeichen, dem kein Escapezeichen vorangestellt ist, beendet. Im folgenden Beispiel wird dem Zeilenumbruchzeichen ein umgekehrter Schrägstrich (**\\**) vorangestellt, wodurch eine „Escapesequenz“ erstellt wird. Diese Escapesequenz bewirkt, dass der Compiler die nächste Zeile als Teil der vorherigen Zeile behandelt. (Weitere Informationen finden Sie unter [Escapesequenzen](../c-language/escape-sequences.md).)  
  
```  
// my comment \  
    i++;   
```  
  
 Daher wird die `i++;`-Anweisung auskommentiert.  
  
 Bei Microsoft C sind die Microsoft-Erweiterungen standardmäßig aktiviert. Verwenden Sie /Za, um diese Erweiterungen zu deaktivieren.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Tokens](../c-language/c-tokens.md)

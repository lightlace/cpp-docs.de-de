---
title: "Schwerwiegender Fehler C1001"
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
  - "C1001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1001"
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

INTERNER COMPILERFEHLER \(Compilerdatei Datei, Zeilennummer\)  
  
 Aufgrund der Kombination eines Ausdrucks und einer Optimierungsoption ist der Compiler u. U. nicht in der Lage, korrekten Code für ein Konstrukt zu generieren.  Versuchen Sie, eine oder mehrere Optimierungsoptionen zu entfernen, und kompilieren Sie die Funktion mit der in der Fehlermeldung angegebenen Zeile neu.  
  
 Sie können das Problem ggf. beheben, indem Sie eine oder mehrere Optimierungsoptionen entfernen.  Um festzustellen, welche Option fehlerhaft ist, entfernen Sie die Optionen nacheinander und führen eine Neukompilierung aus, bis die Fehlermeldung ausbleibt.  Am häufigsten tritt das Problem mit den Optionen **\/Og**, **\/Oi** und `/Oa` auf.  Nachdem Sie die verantwortliche Option ermittelt haben, können Sie sie deaktivieren. Während die Option für das übrige Modul aktiviert bleibt, führen Sie für die Funktion, in der der Fehler aufgetreten ist, das [optimize](../../preprocessor/optimize.md)\-Pragma aus.  
  
 Die Microsoft Knowledge Base hat Weitere Informationen zu C1001; Sie finden [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Schreiben Sie die Zeile mit dem Fehler bzw. einige Codezeilen vor und hinter dieser Zeile neu.
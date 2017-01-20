---
title: "#ifdef- und #ifndef-Direktiven (C/C++)"
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
  - "#ifndef"
  - "#ifdef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#ifdef-Direktive"
  - "#ifndef-Direktive"
  - "ifdef-Direktive (#ifdef)"
  - "ifndef-Direktive (#ifndef)"
  - "Präprozessor, Direktiven"
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# #ifdef- und #ifndef-Direktiven (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Direktiven**\#ifdef** und **\#ifndef** führen dieselbe Funktion aus wie die `#if`\-Direktive, wenn sie mit **defined** \(*Bezeichner*\) verwendet wird.  
  
## Syntax  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## Hinweise  
 Sie können die Direktiven **\#ifdef** und **\#ifndef** überall verwenden, wo auch die Direktive `#if` verwendet werden kann.  Die Anweisung **\#ifdef** *Bezeichner* entspricht `#if 1` , wenn *Bezeichner* definiert wurde, und entspricht `#if 0` , wenn *Bezeichner* nicht definiert wurde oder mit der Direktive `#undef` nicht definiert wurde.  Diese Direktiven überprüfen lediglich, ob die mit `#define` definierten Bezeichner vorhanden sind, und nicht, ob Bezeichner vorhanden sind, die im C\- oder C\+\+\-Quellcode deklariert werden.  
  
 Diese Direktiven werden nur bereitgestellt, um die Kompatibilität mit früheren Versionen der Sprache zu gewährleisten.  Der **defined\(** *Bezeichner* **\)**\-Konstantenausdruck, der mit der `#if`\-Direktive verwendet wird, wird bevorzugt.  
  
 Die **\#ifndef**\-Direktive überprüft das Gegenteil der durch **\#ifdef** geprüften Bedingung.  Wenn der Bezeichner nicht definiert wurde \(oder ihre Definition mit `#undef` entfernt wurde\), ist die Bedingung "true" \(ungleich 0\).  Andernfalls ist die Bedingung "false" \(0\).  
  
 **Microsoft\-spezifisch**  
  
 Der *Bezeichner* kann von der Befehlszeile mithilfe der Option \/D\- übergeben werden.  Bis zu 30 Makros können mit \/D angegeben werden.  
  
 Dies ist hilfreich, wenn überprüft werden soll, ob eine Definition vorhanden ist, da diese von der Befehlszeile übergeben werden kann.  Beispiel:  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)
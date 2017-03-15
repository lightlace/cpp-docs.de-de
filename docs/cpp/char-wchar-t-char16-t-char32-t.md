---
title: "char, wchar_t, char16_t, char32_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "char_cpp"
  - "char16_t_cpp"
  - "whchar_t_cpp"
  - "char32_t_cpp"
dev_langs: 
  - "C++"
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# char, wchar_t, char16_t, char32_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Typen char, wchar\_t, char16\_t und char32\_t sind integrierte Typen, die alphanumerische Zeichen, alphanumerische Glyphen und Zeichen darstellen, die nicht gedruckt werden können.  char weist eine Größe von 8 Bit, wchar\_t und char16\_t von 16 Bit und char32\_t von 32 Bit auf.  
  
## Syntax  
  
```vb  
char     ch1{ 'a' };  
wchar_t  ch2{ 'a' }; // or {L'a'}  
char16_t ch3{ L'a' };// or {L'a'}  
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## Hinweise  
 Der `char`\-Typ war der ursprüngliche Zeichentyp in C und C\+\+.  Dieser kann zum Speichern von Zeichen aus dem ASCII\-Zeichensatz, einem ISO\-8859\-Zeichensatz oder dem UTF\-8\-Zeichensatz verwendet werden.  Der Typ `unsigned char` wird häufig zur Darstellung eines *Bytes* verwendet, bei dem es nicht um einen in C\+\+ integrierten Typ handelt.  Der char\-Typ ist für den Text in zahlreichen Sprachen nicht geeignet.  Im Allgemeinen sollten moderne Programme zur Darstellung von Text Breitzeichentypen verwenden.  Unicode ist  
  
 Der basic\_string\-Typ ist in der C\+\+\-Standardbibliothek weist Spezialisierungen für schmale und Breitzeichenfolgen auf.  Verwenden Sie std::string für Zeichen vom Typ char und std::wstring, wenn die Zeichen vom Typ wchar\_t sind.  Andere Typen zur Darstellung von Text einschließlich std::stringstream und std::cout weisen Spezialisierungen für schmale und Breitzeichenfolgen auf.  
  
## Anforderungen
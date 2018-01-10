---
title: Char, Wchar_t, char16_t und char32_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs: C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c01d4718bbc1781ea4705945bb90874384e09058
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
Die Typen char, wchar_t, char16_t und char32_t sind integrierte Typen, die alphanumerische Zeichen, alphanumerische Glyphen und Zeichen darstellen, die nicht gedruckt werden können. char weist eine Größe von 8 Bit, wchar_t und char16_t von 16 Bit und char32_t von 32 Bit auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
char     ch1{ 'a' };    
wchar_t  ch2{ 'a' }; // or {L'a'}    
char16_t ch3{ L'a' };// or {L'a'}    
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## <a name="remarks"></a>Hinweise  
 Der `char`-Typ war der ursprüngliche Zeichentyp in C und C++. Dieser kann zum Speichern von Zeichen aus dem ASCII-Zeichensatz, einem ISO-8859-Zeichensatz oder dem UTF-8-Zeichensatz verwendet werden. Der Typ `unsigned char` häufig zur Darstellung einer *Byte* einen integrierten Typ in C++ ist. Der char-Typ ist für den Text in zahlreichen Sprachen nicht geeignet. Im Allgemeinen sollten moderne Programme zur Darstellung von Text Breitzeichentypen verwenden. Unicode ist  
  
 Der basic_string-Typ ist in der C++-Standardbibliothek weist Spezialisierungen für schmale und Breitzeichenfolgen auf. Verwenden Sie std::string für Zeichen vom Typ char und std::wstring, wenn die Zeichen vom Typ wchar_t sind. Andere Typen zur Darstellung von Text einschließlich std::stringstream und std::cout weisen Spezialisierungen für schmale und Breitzeichenfolgen auf.  
  

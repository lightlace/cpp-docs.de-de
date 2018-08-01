---
title: Char, Wchar_t, char16_t, char32_t | Microsoft-Dokumentation
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs:
- C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d0c89df02c624d96c613f6241c9beefd466827e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402613"
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
Die Typen **Char**, **"wchar_t"**, **char16_t** und **char32_t** sind integrierte Typen, die alphanumerische Zeichen darstellen sowie alphanumerische Glyphen und nicht druckbaren Zeichen.

## <a name="syntax"></a>Syntax

```cpp  
char     ch1{ 'a' };  // or { u8'a' }   
wchar_t  ch2{ L'a' };    
char16_t ch3{ u'a' };    
char32_t ch4{ U'a' };  
```  
  
## <a name="remarks"></a>Hinweise

Die **Char** Typ war der ursprüngliche Zeichentyp in C und C++. Der Typ **unsigned Char** dient häufig zur Darstellung einer *Byte*, dem ist nicht in C++ ein integrierter Typ. Die **Char** Typ zum Speichern von Zeichen aus dem ASCII-Zeichensatz oder keines der ISO-8859-Zeichensatz und einzelnen Bytes der Multibyte-Zeichen, z. B. Shift-JIS oder UTF-8-Codierung von Unicode-Zeichensatz verwendet werden kann. Zeichenfolgen **Char** Typ werden als bezeichnet *eingrenzen* Zeichenfolgen, selbst wenn verwendet, um Multi-Byte-Zeichen zu codieren. In der Microsoft-Compiler **Char** ist ein 8-Bit-Typ.

Die **"wchar_t"** Typ ist ein Breitzeichen Implementierung definierten Typ. In der Microsoft-Compiler, stellt es ein 16-Bit-Breitzeichen, die zum Speichern von Unicode-codiert als UTF-16LE, verwendet die systemeigenen Zeichentyp auf Windows-Betriebssystemen. Die Breitzeichenversionen von Funktionen verwenden die Universal C Runtime (UCRT) **"wchar_t"** und die Zeiger und das Array als Parameter und Rückgabewerte, Typen, wie auch die Breitzeichenversionen der systemeigenen Windows-API.

Die **char16_t** und **char32_t** Typen darstellen bzw. die 16-Bit- und 32-Bit-Breitzeichen. Unicode codiert als UTF-16 in gespeichert werden, kann die **char16_t** Typ und Unicode-codiert als UTF-32 in gespeichert werden, kann die **char32_t** Typ. Zeichenfolgen, die diese Typen und **"wchar_t"** werden alle als bezeichnet *wide* Zeichenfolgen, obwohl der Begriff häufig speziell für Zeichenfolgen bezieht sich **"wchar_t"** Typ.

In der C++-Standardbibliothek die `basic_string` Typ speziell für schmale und breitzeichenfolgen. Verwendung `std::string` Wenn die Zeichen sind vom Typ **Char**, `std::u16string` Wenn die Zeichen sind vom Typ **char16_t**, `std::u32string` Wenn die Zeichen sind vom Typ **char32_t** , und `std::wstring` Wenn die Zeichen sind vom Typ **"wchar_t"**. Andere Typen, die Darstellung von Text, einschließlich `std::stringstream` und `std::cout` weisen spezialisierungen für schmale und breitzeichenfolgen.  
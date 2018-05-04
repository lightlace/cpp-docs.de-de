---
title: Char, Wchar_t, char16_t und char32_t | Microsoft Docs
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
ms.openlocfilehash: 2dc38eb9742459139747578a8227bdfaee8bb8a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
Die Typen **Char**, **Wchar_t**, **char16_t** und **char32_t** sind integrierte Typen, die alphanumerische Zeichen darstellen sowie nicht-alphanumerische Glyphen und nicht druckbaren Zeichen.

## <a name="syntax"></a>Syntax

```cpp  
char     ch1{ 'a' };  // or { u8'a' }   
wchar_t  ch2{ L'a' };    
char16_t ch3{ u'a' };    
char32_t ch4{ U'a' };  
```  
  
## <a name="remarks"></a>Hinweise

Die **Char** Typ war der ursprüngliche Zeichentyp in C und C++. Der Typ **unsigned Char** häufig zur Darstellung einer *Byte*, einen integrierten Typ in C++ ist. Die **Char** -Typ kann zum Speichern von Zeichen aus dem ASCII-Zeichensatz oder keines der ISO-8859-Zeichensätze, und einzelne Bytes von Multi-Byte-Zeichen, z. B. Shift-JIS oder UTF-8-Codierung von Unicode-Zeichensatz verwendet werden. Zeichenfolgen in **Char** Typ als bezeichnet *eingrenzen* Zeichenfolgen, selbst wenn verwendet, um Multi-Byte-Zeichen zu codieren. In der Microsoft-Compiler **Char** ist ein 8-Bit-Typ.

Die **Wchar_t** Typ ist ein Breitzeichen Implementierung definierten Typ. In der Microsoft-Compiler, stellt er ein 16-Bit-Breitzeichen, die zum Speichern von Unicode codiert als UTF-16LE verwendet die systemeigenen Zeichentyp auf Windows-Betriebssystemen. Die Breitzeichenversionen der Universal C Runtime (UCRT) Library-Funktionen verwenden **Wchar_t** und seine Zeiger und das Array als Parameter und Rückgabewerte, Typen, wie die Breitzeichenversionen der systemeigene Windows-API.

Die **char16_t** und **char32_t** Typen 16-Bit- und 32-Bit-Breitzeichen bzw. darstellen. Unicode codiert als UTF-16 kann, in gespeichert werden der **char16_t** Typ und Unicode codiert als UTF-32 kann, in gespeichert werden der **char32_t** Typ. Zeichenfolgen dieser Typen und **Wchar_t** sind als alle genannten *wide* Zeichenfolgen, obwohl der Begriff häufig speziell für die Zeichenfolgen der bezieht sich **Wchar_t** Typ.

In der C++-Standardbibliothek der `basic_string` Typ für schmale und breitzeichenfolgen spezialisiert ist. Verwendung `std::string` Wenn sind die Zeichen vom Typ **Char**, `std::u16string` Wenn sind die Zeichen vom Typ **char16_t**, `std::u32string` Wenn sind die Zeichen vom Typ **char32_t** , und `std::wstring` Wenn sind die Zeichen vom Typ **Wchar_t**. Andere Typen, die Darstellung von Text einschließlich `std::stringstream` und `std::cout` weisen spezialisierungen für schmale und breitzeichenfolgen.  
  

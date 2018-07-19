---
title: Nothrow (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/03/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7efbd22c846327c5731cf3ab14ba1f2045c8636f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939148"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft-spezifisch**

Ein **__declspec** erweiterten Attribut, das in der Deklaration von Funktionen verwendet werden kann.

## <a name="syntax"></a>Syntax  
  
> *der Rückgabetyp* __declspec(nothrow) [*Aufruf-Konvention*] *Funktionsname-* ([*Argumentliste*])

## <a name="remarks"></a>Hinweise

Es wird empfohlen, alle neuer Code verwenden, die ["noexcept"](noexcept-cpp.md) Operator statt `__declspec(nothrow)`.

Dieses Attribut weist den Compiler an, dass die deklarierte Funktion und die Funktionen, die aufgerufen werden, nie eine Ausnahme auslösen. Es erzwingt allerdings nicht der Richtlinie. Das heißt, sie löst nie [Std:: Terminate](../standard-library/exception-functions.md#terminate) aufgerufen werden soll, im Gegensatz zu `noexcept`, oder im **Std: c ++ 17** Modus (Visual Studio 2017 Version 15.5 und höher), `throw()`.

Mit dem Modell für synchrone Ausnahmebehandlung kann der Compiler nun standardmäßig die Mechanismen der Lebensdauerverfolgung gewisser entladbarer Objekte in einer solchen Funktion eliminieren, wodurch die Codegröße erheblich reduziert wird. Wenn die folgende präprozessoranweisung, die drei Funktionsdeklarationen gleichwertig sind in **/Std: c ++ 14** Modus:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

In **/Std: c ++ 17** Modus `throw()` entspricht nicht den anderen, mit denen `__declspec(nothrow)` , da es bewirkt, dass `std::terminate` aufgerufen werden, wenn von der Funktion eine Ausnahme ausgelöst wird.

Die `void __stdcall f3() throw();` Deklaration verwendet die Syntax von C++-Standard definiert. In C ++ 17 der `throw()` Schlüsselwort wurde als veraltet markiert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[Schlüsselwörter](../cpp/keywords-cpp.md)  

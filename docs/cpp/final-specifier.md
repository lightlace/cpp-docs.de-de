---
title: final-Bezeichner
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: c6400c8060664713fdd004a5aa9536e0617bc0c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588083"
---
# <a name="final-specifier"></a>final-Bezeichner

Können Sie die **endgültige** Schlüsselwort, um virtuelle Funktionen festzulegen, die in einer abgeleiteten Klasse überschrieben werden kann. Sie können es auch verwenden, um Klassen festzulegen, die nicht vererbbar sind.

## <a name="syntax"></a>Syntax

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>Hinweise

**letzte** ist kontextbezogen und hat eine besonderen Bedeutung, nur, wenn er wird verwendet, nach der Deklaration einer Funktion oder Klasse; anderenfalls, es kein reserviertes Schlüsselwort ist.

Wenn **endgültige** wird verwendet, in den Klassendeklarationen `base-classes` ist ein optionaler Teil der Deklaration.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die **endgültige** Schlüsselwort, um anzugeben, dass eine virtuelle Funktion nicht überschrieben werden kann.

```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // compiler error: attempting to
                         // override a final function
};
```

Weitere Informationen zur Verwendung, um anzugeben, dass Memberfunktionen überschrieben werden können, finden Sie unter [Überschreibungsspezifizierer](../cpp/override-specifier.md).

Im nächsten Beispiel wird die **endgültige** Schlüsselwort, um anzugeben, dass eine Klasse nicht geerbt werden kann.

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[override-Bezeichner](../cpp/override-specifier.md)
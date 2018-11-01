---
title: __raise
ms.date: 11/04/2016
f1_keywords:
- __raise
- __raise_cpp
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
ms.openlocfilehash: 865524fe91b7d137e3a943973dcca6d833bd16df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471434"
---
# <a name="raise"></a>__raise

Hebt die Aufrufsite eines Ereignisses hervor.

## <a name="syntax"></a>Syntax

```
__raise method-declarator;
```

## <a name="remarks"></a>Hinweise

Aus verwaltetem Code kann ein Ereignis nur innerhalb der Klasse ausgelöst werden, in der es definiert ist. Finden Sie unter [Ereignis](../windows/event-cpp-component-extensions.md) für Weitere Informationen.

Das Schlüsselwort **__raise** verursacht einen Fehler, wenn Sie einem nicht ereignisgebundenen Aufruf ausgegeben werden soll.

> [!NOTE]
>  Eine von einer Vorlage gebildete Klasse oder Struktur kann keine Ereignisse enthalten.

## <a name="example"></a>Beispiel

```cpp
// EventHandlingRef_raise.cpp
struct E {
   __event void func1();
   void func1(int) {}

   void func2() {}

   void b() {
      __raise func1();
      __raise func1(1);  // C3745: 'int Event::bar(int)':
                         // only an event can be 'raised'
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func1();
   __raise e.func1(1);  // C3745
   __raise e.func2();   // C3745
}
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[Ereignisbehandlung](../cpp/event-handling.md)<br/>
[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)
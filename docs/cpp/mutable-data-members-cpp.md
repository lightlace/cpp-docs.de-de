---
title: Änderbare Datenmember (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: 8d592eb97f70bfc26c075317c57ec4d5c78e3956
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301590"
---
# <a name="mutable-data-members-c"></a>Änderbare Datenmember (C++)

Dieses Schlüsselwort kann nur auf nicht statische und nicht konstante Datenmember einer Klasse angewendet werden. Wenn ein Datenmember deklariert wird **änderbare**, ist es zulässig, die dieses Datenelement aus einen Wert zuweisen einer **const** Member-Funktion.

## <a name="syntax"></a>Syntax

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>Hinweise

Beispielsweise wird der folgende Code ohne Fehler kompiliert, da `m_accessCount` deklariert wurde, werden **änderbare**, und kann daher geändert werden, indem `GetFlag` , obwohl `GetFlag` eine const-Memberfunktion ist.

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)
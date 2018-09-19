---
title: Änderbare Datenmember (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de0a208341e6a687d1319c4d8d60cc8671555dd6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106993"
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
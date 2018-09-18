---
title: Compilerwarnung (Stufe 1) C4190 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d398331c159c6fc639160dbe54d6ab5f969d3dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063735"
---
# <a name="compiler-warning-level-1-c4190"></a>Compilerwarnung (Stufe 1) C4190

'Bezeichner1' C-Bindung angegeben wurde, aber gibt UDT "Bezeichner2" ist nicht mit C

Eine Funktion oder ein Zeiger auf Funktion verfügt über ein UDT (benutzerdefinierte Typ, die eine Klasse, Struktur, Enumeration oder Union ist) als Rückgabetyp und `extern` "C"-Verknüpfung. Dies ist zulässig wenn:

- Alle Aufrufe dieser Funktion auftreten von C++.

- Die Definition der Funktion ist in C++.

## <a name="example"></a>Beispiel

```cpp
// C4190.cpp
// compile with: /W1 /LD
struct X
{
   int i;
   X ();
   virtual ~X ();
};

extern "C" X func ();   // C4190
```
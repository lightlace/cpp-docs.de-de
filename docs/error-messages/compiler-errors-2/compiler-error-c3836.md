---
title: Compilerfehler C3836 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3836
dev_langs:
- C++
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a1349ff88c00f8091a8187bb963f4fb683b694e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046029"
---
# <a name="compiler-error-c3836"></a>Compilerfehler C3836

statischer Konstruktor darf keine Memberinitialisiererliste haben

Eine verwaltete Klasse kann keinen statischen Konstruktor haben, der auch ein Member-Initialisierungsliste aufweist. Konstruktoren von statischen Klassen werden von der common Language Runtime-Initialisierung beim Initialisieren von statischen Datenmembern Klasse aufgerufen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3836 generiert:

```
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```

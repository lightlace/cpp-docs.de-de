---
title: Compilerfehler C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: 33860273db07894a9a4d15ba6d578598a18819ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477544"
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

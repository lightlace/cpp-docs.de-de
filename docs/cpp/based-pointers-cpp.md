---
title: Basierte Zeiger (C++)
ms.date: 10/09/2018
f1_keywords:
- __based
- _based
- __based_cpp
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
ms.openlocfilehash: 771d3ee132e4cd63499fec886ef9f7cd06ec0260
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676368"
---
# <a name="based-pointers-c"></a>Basierte Zeiger (C++)

**Microsoft-spezifisch**

Die **__based** Schlüsselwort können Sie zum Deklarieren von Zeigern basierend auf Zeigern (Zeiger, die Offsets von vorhandenen Zeigern sind).

## <a name="syntax"></a>Syntax

```

type __based( base ) declarator
```

## <a name="remarks"></a>Hinweise

Zeiger, die auf Zeigeradressen basieren, sind die einzige Form des der **__based** Schlüsselworts, das in 32-Bit oder 64-Bit-Kompilierungen gültig. Für den 32-Bit-C/C++Compiler von Microsoft ist ein basierter Zeiger ein 32-Bit-Offset von einer 32-Bit-Zeigerbasis. Eine ähnliche Einschränkung besteht für 64-Bit-Umgebungen, in denen ein basierter Zeiger ein 64-Bit-Offset von der 64-Bit-Basis ist.

Eine Verwendung von Zeigern, die auf Zeigern basieren, ist für dauerhafte Bezeichner, die Zeiger enthalten. Eine verknüpfte Liste, die aus Zeigern auf Grundlage eines Zeigers besteht, kann auf Datenträger gespeichert werden, dann an eine andere Stelle im Arbeitsspeicher neu geladen werden, wobei die Zeiger weiterhin gültig bleiben. Zum Beispiel:

```cpp
// based_pointers1.cpp
// compile with: /c
void *vpBuffer;
struct llist_t {
   void __based( vpBuffer ) *vpData;
   struct llist_t __based( vpBuffer ) *llNext;
};
```

Dem Zeiger `vpBuffer` wird die Adresse des später im Programm zugewiesenen Arbeitsspeichers zugeteilt. Die verknüpfte Liste wird relativ zum Wert von `vpBuffer` verschoben.

> [!NOTE]
>  Beibehalten von Bezeichnern, die Zeiger können auch vorgenommen werden, indem Sie mithilfe von [Speicherabbilddateien](/windows/desktop/Memory/file-mapping).

Beim Dereferenzieren eines basierten Zeigers muss die Basis explizit angegeben werden oder implizit durch die Deklaration bekannt sein.

Für die Kompatibilität mit früheren Versionen **_basierend** ist ein Synonym für **__based** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md) ist angegeben.

## <a name="example"></a>Beispiel

Im folgenden Code wird gezeigt, wie ein Basiszeiger verändert wird, indem seine Basis geändert wird.

```cpp
// based_pointers2.cpp
// compile with: /EHsc
#include <iostream>

int a1[] = { 1,2,3 };
int a2[] = { 10,11,12 };
int *pBased;

typedef int __based(pBased) * pBasedPtr;

using namespace std;
int main() {
   pBased = &a1[0];
   pBasedPtr pb = 0;

   cout << *pb << endl;
   cout << *(pb+1) << endl;

   pBased = &a2[0];

   cout << *pb << endl;
   cout << *(pb+1) << endl;
}
```

```Output
1
2
10
11
```

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[alloc_text](../preprocessor/alloc-text.md)
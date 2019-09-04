---
title: init_seg-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
ms.openlocfilehash: 5e57ea0eedfc1df6e196391c5edd3acfbad0a7c7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221006"
---
# <a name="init_seg-pragma"></a>init_seg-Pragma

**C++Zugeschnitten**

Gibt ein Schlüsselwort oder einen Codeabschnitt an, der sich auf die Reihenfolge auswirkt, in der Startcode ausgeführt wird.

## <a name="syntax"></a>Syntax

> **#pragma init_seg (** { **Compiler** | **lib** | **User** | "*section-Name*" [ **,** *Func-Name* ]} **)**

## <a name="remarks"></a>Hinweise

Die Begriffe *Segment* und *Abschnitt* haben dieselbe Bedeutung in diesem Artikel.

Da Code manchmal zum Initialisieren globaler statischer Objekte erforderlich ist, müssen Sie angeben, wann die Objekte zu erstellen sind. Insbesondere ist es wichtig, das **init_seg** -Pragma in Dynamic Link Libraries (DLLs) oder in Bibliotheken zu verwenden, die eine Initialisierung erfordern.

Die Optionen für das **init_seg** -Pragma lauten wie folgt:

**Versionen**\
Reserviert für die Initialisierung der Microsoft C-Laufzeitbibliothek. Objekte in dieser Gruppe werden zuerst erstellt.

**lib**\
Verfügbar für die Initialisierungen der Klassenbibliotheken von Drittanbietern. Objekte in dieser Gruppe werden erstellt, nachdem Sie als **Compiler**gekennzeichnet sind, aber vor allen anderen.

**Bedienungs**\
Verfügbar für alle beliebigen Benutzer. Objekte in dieser Gruppe werden zuletzt erstellt.

*Abschnitts Name*\
Ermöglicht die explizite Angabe des Abschnitts für Initialisierung. Objekte in einem vom Benutzer angegebenen *Abschnittsnamen* werden nicht implizit erstellt. Die Adressen werden jedoch in dem Abschnitt platziert, der durch *Abschnitts Name*benannt wird.

Der von Ihnen fest Zugende *Abschnitts Name* enthält Verweise auf Hilfsfunktionen, die die globalen Objekte erstellen, die nach dem Pragma in diesem Modul deklariert werden.

Eine Liste der Namen, die Sie beim Erstellen eines Abschnitts nicht verwenden sollten, finden Sie unter [/section](../build/reference/section-specify-section-attributes.md).

*Func-Name*\
Gibt eine Funktion an, die statt `atexit` aufgerufen werden soll, wenn das Programm beendet wird. Diese Hilfsfunktion ruft auch [atexit](../c-runtime-library/reference/atexit.md) mit einem Zeiger auf den Dekonstruktor für das globale Objekt auf. Wenn Sie einen Funktionsbezeichner im Pragma des Formulars angeben,

```cpp
int __cdecl myexit (void (__cdecl *pf)(void))
```

wird die Funktion anstelle von `atexit` für die Laufzeitbibliothek von C aufgerufen. Sie können eine Liste der Dekonstruktoren erstellen, die aufgerufen werden sollen, wenn Sie bereit sind, die Objekte zu zerstören.

Wenn Sie die Initialisierung verzögern müssen (z. B. in einer DLL), können Sie den Abschnittsnamen auch explizit angeben. Der Code muss dann die Konstruktoren für jedes statische Objekt aufzurufen.

Der Bezeichner für die Ersetzung von `atexit` weist keine Anführungszeichen auf.

Ihre Objekte werden weiterhin in den Abschnitten abgelegt, die von den anderen `XXX_seg` Pragmas definiert werden.

Die im Modul deklarierten Objekte werden nicht automatisch von der C-Laufzeit initialisiert. Der Code muss die Initialisierung durchführen.

Standardmäßig sind `init_seg`-Abschnitte schreibgeschützt. Wenn der Abschnitts Name ist `.CRT`, ändert der Compiler das Attribut im Hintergrund in den schreibgeschützten Modus, selbst wenn er als Lese-/Schreibzugriff markiert ist.

**Init_seg** können in einer Übersetzungseinheit nicht mehrmals angegeben werden.

Auch wenn das Objekt über keinen benutzerdefinierten Konstruktor verfügt, der explizit im Code definiert ist, generiert der Compiler möglicherweise einen für Sie. Beispielsweise kann er eine erstellen, um v-Table-Zeiger zu binden. Wenn dies erforderlich ist, ruft der Code den vom Compiler generierten Konstruktor auf.

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_init_seg.cpp
#include <stdio.h>
#pragma warning(disable : 4075)

typedef void (__cdecl *PF)(void);
int cxpf = 0;   // number of destructors we need to call
PF pfx[200];    // pointers to destructors.

int myexit (PF pf) {
   pfx[cxpf++] = pf;
   return 0;
}

struct A {
   A() { puts("A()"); }
   ~A() { puts("~A()"); }
};

// ctor & dtor called by CRT startup code
// because this is before the pragma init_seg
A aaaa;

// The order here is important.
// Section names must be 8 characters or less.
// The sections with the same name before the $
// are merged into one section. The order that
// they are merged is determined by sorting
// the characters after the $.
// InitSegStart and InitSegEnd are used to set
// boundaries so we can find the real functions
// that we need to call for initialization.

#pragma section(".mine$a", read)
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;

#pragma section(".mine$z",read)
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;

// The comparison for 0 is important.
// For now, each section is 256 bytes. When they
// are merged, they are padded with zeros. You
// can't depend on the section being 256 bytes, but
// you can depend on it being padded with zeros.

void InitializeObjects () {
   const PF *x = &InitSegStart;
   for (++x ; x < &InitSegEnd ; ++x)
      if (*x) (*x)();
}

void DestroyObjects () {
   while (cxpf>0) {
      --cxpf;
      (pfx[cxpf])();
   }
}

// by default, goes into a read only section
#pragma init_seg(".mine$m", myexit)

A bbbb;
A cccc;

int main () {
   InitializeObjects();
   DestroyObjects();
}
```

```Output
A()
A()
A()
~A()
~A()
~A()
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

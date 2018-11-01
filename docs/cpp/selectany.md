---
title: selectany
ms.date: 11/04/2016
f1_keywords:
- selectany_cpp
helpviewer_keywords:
- __declspec keyword [C++], selectany
- selectany __declspec keyword
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
ms.openlocfilehash: a6bf4076dfecbd29035716285f52c0a9faf81067
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623755"
---
# <a name="selectany"></a>selectany

**Microsoft-spezifisch**

Weist den Compiler an, dass das deklarierte, globale Datenelement (Variable oder Objekt) ein beliebig auswählbares COMDAT (eine Paketfunktion) ist.

## <a name="syntax"></a>Syntax

```
__declspec( selectany ) declarator
```

## <a name="remarks"></a>Hinweise

Wenn zum Zeitpunkt der Verknüpfung mehrere Definitionen einer COMDAT angezeigt werden, wählt der Linker eine aus und verwirft den Rest. Wenn die Linkeroption [/OPT: REF](../build/reference/opt-optimizations.md) (Optimizations) ausgewählt ist, und klicken Sie dann die COMDAT-Eliminierung erfolgt, um alle unreferenzierten Datenelemente in der Linkerausgabe zu entfernen.

Konstruktoren und Zuweisung durch globale Funktion oder statische Methoden in der Deklaration erstellen keine Verweise und verhindern die /OPT: REF-Eliminierung nicht. Nebeneffekte von derartigem Code sollten nicht davon abhängen, ob keine weiteren Verweise auf die Daten vorhanden sind.

Für dynamisch initialisierten, globalen Objekte **Selectany** wird ein Objekt ohne Verweis Initialisierungscode, auch verwerfen.

Ein globales Datenelement kann normalerweise nur einmal in einem EXE- bzw. DLL-Projekt initialisiert werden. **Selectany** kann verwendet werden, beim Initialisieren der globale Daten, die durch Header definiert sind, wenn derselbe Header in mehr als einer Quelldatei angezeigt wird. **Selectany** in C- und C++-Compilern verfügbar ist.

> [!NOTE]
>  **Selectany** kann nur angewendet werden, auf die tatsächliche Initialisierung globaler Datenelemente, die extern sichtbar sind.

## <a name="example"></a>Beispiel

Dieser Code zeigt, wie Sie mit der **Selectany** Attribut:

```cpp
//Correct - x1 is initialized and externally visible
__declspec(selectany) int x1=1;

//Incorrect - const is by default static in C++, so
//x2 is not visible externally (This is OK in C, since
//const is not by default static in C)
const __declspec(selectany) int x2 =2;

//Correct - x3 is extern const, so externally visible
extern const __declspec(selectany) int x3=3;

//Correct - x4 is extern const, so it is externally visible
extern const int x4;
const __declspec(selectany) int x4=4;

//Incorrect - __declspec(selectany) is applied to the uninitialized
//declaration of x5
extern __declspec(selectany) int x5;

// OK: dynamic initialization of global object
class X {
public:
X(int i){i++;};
int i;
};

__declspec(selectany) X x(1);
```

## <a name="example"></a>Beispiel

Dieser Code zeigt, wie Sie mit der **Selectany** Attribut, um sicherzustellen, dass Daten COMDAT-Faltung, wenn Sie auch die [/OPT: ICF](../build/reference/opt-optimizations.md) -Linkeroption. Beachten Sie, dass die Daten mit markiert sein müssen **Selectany** und platziert Sie in eine **const** (Readonly)-Abschnitt. Sie müssen den schreibgeschützten Abschnitt explizit angeben.

```cpp
// selectany2.cpp
// in the following lines, const marks the variables as read only
__declspec(selectany) extern const int ix = 5;
__declspec(selectany) extern const int jx = 5;
int main() {
   int ij;
   ij = ix + jx;
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)
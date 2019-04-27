---
title: Compilerwarnung (Stufe 1) C4743
ms.date: 11/04/2016
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: d17fd65f1108aab6e3ce97ec75c0ffb899c06cda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152007"
---
# <a name="compiler-warning-level-1-c4743"></a>Compilerwarnung (Stufe 1) C4743

"*Typ*"hat eine unterschiedliche Größe "*" file1 "*'und'*Datei2*': *Anzahl* und *Anzahl* Bytes

Eine externe Variable verwiesen wird, oder in zwei Dateien definiert verfügt über verschiedene Arten in diesen Dateien aus, und der Compiler bestimmt, die die Größe der Variablen im *"file1"* unterscheidet sich von der Größe der Variablen im *Datei2*.

Es gibt wichtig Fall, wenn diese Warnung für C++ ausgegeben werden kann. Wenn Sie mit dem gleichen Namen in zwei verschiedenen Dateien, die gleichen Typen deklarieren, wenn diese Deklarationen auf virtuelle Funktionen enthalten, und die Deklarationen nicht identisch sind, kann der Compiler die Warnung C4744 für die virtuelle Funktion, die Tabellen ausgeben. Die Warnung tritt auf, da es zwei unterschiedliche Größe virtuelle Funktionstabellen für den gleichen Typ gibt und Linker muss auswählen, eine davon in die ausführbare Datei integriert.  Es ist möglich, dass dies in Ihrem Programm Aufrufen der falschen virtuellen Funktions führen kann.

Um diese Warnung zu beheben, verwenden Sie die gleichen Typdefinition oder verwenden Sie unterschiedliche Namen für die Typen oder Variablen.

## <a name="example"></a>Beispiel

Dieses Beispiel enthält eine Definition des Typs.

```
// C4743a.cpp
// compile with: /c
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
};

void C::f1(void) {}
void C::f2(void) {}
void C::f3(void) {}
C q;
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4743 generiert.

```
// C4743b.cpp
// compile with: C4743a.cpp /W1 /GL /O2
// C4743 expected
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
    virtual void f4(void);
    virtual void f5(void);
};

void C::f4(void) {}
void C::f5(void) {}
C x;

int main() {}
```
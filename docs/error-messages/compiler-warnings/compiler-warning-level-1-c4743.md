---
title: Compilerwarnung (Stufe 1) C4743
ms.date: 05/13/2019
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: 53ead0e34b55eca44399cee09f1947a12e1eadd3
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611830"
---
# <a name="compiler-warning-level-1-c4743"></a>Compilerwarnung (Stufe 1) C4743

"*Typ*"hat eine unterschiedliche Größe "*" file1 "*'und'*Datei2*': *Anzahl* und *Anzahl* Bytes

Eine externe Variable verwiesen wird, oder in zwei Dateien definiert verfügt über verschiedene Arten in diesen Dateien aus, und der Compiler bestimmt, die die Größe der Variablen im *"file1"* unterscheidet sich von der Größe der Variablen im *Datei2*.

## <a name="remarks"></a>Hinweise

Es ist ein wichtiger Fall, wenn es sich bei für diese Warnung ausgegeben werden kann C++. Wenn Sie mit dem gleichen Namen in zwei verschiedenen Dateien, die gleichen Typen deklarieren, wenn diese Deklarationen auf virtuelle Funktionen enthalten, und die Deklarationen nicht identisch sind, kann der Compiler die Warnung C4744 für die virtuelle Funktion, die Tabellen ausgeben. Die Warnung tritt auf, da es zwei virtuelle Funktion, die unterschiedlich großen Tabellen für den gleichen Typ gibt und Linker muss auswählen, eine davon in die ausführbare Datei integriert.  Es ist möglich, dass es in Ihrem Programm Aufrufen der falschen virtuellen Funktions führen kann.

Um diese Warnung zu beheben, verwenden Sie die gleichen Typdefinition oder verwenden Sie unterschiedliche Namen für die Typen oder Variablen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4743 generiert. Um es zu kompilieren, platzieren Sie beide Dateien im selben Ordner, und führen Sie  

```cmd
cl /EHsc /W1 /GL /O2 C4743a.cpp C4743b.cpp
```

```cpp
// C4743a.cpp
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

```cpp
// C4743b.cpp
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

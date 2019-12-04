---
title: Compilerfehler C2813
ms.date: 11/04/2016
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
ms.openlocfilehash: b36e966d897b1a3f9a4f601ef281091160da34c3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750935"
---
# <a name="compiler-error-c2813"></a>Compilerfehler C2813

\#Import wird bei/MP nicht unterstützt.

C2813 wird ausgegeben, wenn Sie in einem Compilerbefehl die **/MP** -Compileroption und zwei oder mehr zu kompilierende Dateien angeben, von denen mindestens eine Datei die[#import](../../preprocessor/hash-import-directive-cpp.md) -Präprozessordirektive enthält. Die [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive generiert C++-Klassen aus den Typen in der angegebenen Typbibliothek und schreibt diese Klassen dann in zwei Headerdateien. Die [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive wird nicht unterstützt. Wenn mehrere Kompilierungseinheiten dieselbe Typbibliothek importieren, tritt zwischen diesen Einheiten ein Konflikt auf, wenn sie versuchen, die gleichen Headerdateien zur gleichen Zeit zu schreiben.

Dieser Compilerfehler und die **/MP** -Compileroption sind neu in Visual Studio 2008.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2813 generiert. Die Befehlszeile im "compile with:"-Kommentar weist den Compiler an, die Compileroptionen **/MP** und **/c** zum Kompilieren mehrerer Dateien zu verwenden. Mindestens eine der Dateien enthält die [#import](../../preprocessor/hash-import-directive-cpp.md) -Direktive. Zum Testen dieses Beispiels wird die gleiche Datei zweimal verwendet.

```cpp
// C2813.cpp
// compile with: /MP /c C2813.cpp C2813.cpp
#import "C:\windows\system32\stdole2.tlb"   // C2813
int main()
{
}
```

---
title: comment-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.comment
- comment_CPP
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
ms.openlocfilehash: 3175ad5318bcc6fd9aa6233258ccec9033c89be8
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219096"
---
# <a name="comment-pragma"></a>comment-Pragma

Platziert einen Kommentardatensatz in einer Objektdatei oder ausführbaren Datei.

## <a name="syntax"></a>Syntax

> **#pragma Kommentar (** *comment-Type* [ **,** "*comment-String*"] **)**

## <a name="remarks"></a>Hinweise

Der *Kommentartyp* ist einer der unten beschriebenen vordefinierten Bezeichner, der den Typ des Kommentar Datensatzes angibt. Die optionale *Kommentar Zeichenfolge* ist eine Zeichenfolgenliterale, die zusätzliche Informationen für einige Kommentar Typen bereitstellt. Da *comment-String* ein Zeichenfolgenliteralzeichen ist, werden alle Regeln für Zeichen folgen Literale in Bezug auf Escapezeichen,`"`eingebettete Anführungszeichen () und Verkettung befolgt.

### <a name="compiler"></a>Compiler

Platziert den Namen und die Versionsnummer des Compilers in der Objektdatei. Dieser Kommentardatensatz wird vom Linker ignoriert. Wenn Sie einen *Kommentarzeichen* Folgen Parameter für diesen Daten Satz Typen angeben, generiert der Compiler eine Warnung.

### <a name="lib"></a>lib

Platziert einen einen Datensatz für Bibliothekssuchvorgänge in der Objektdatei. Dieser Kommentartyp muss von einem *Kommentarzeichen* Folgen Parameter begleitet werden, der den Namen (und möglicherweise den Pfad) der Bibliothek enthält, die der Linker durchsuchen soll. Der Bibliotheksname folgt den standardmäßigen Bibliotheks Such Datensätzen in der Objektdatei. der Linker sucht diese Bibliothek so, als ob Sie Sie in der Befehlszeile benannt hätten, vorausgesetzt, dass die Bibliothek nicht mit [/NODEFAULTLIB](../build/reference/nodefaultlib-ignore-libraries.md)angegeben wird. Sie können mehrere Datensätze an Bibliothekssuchvorgängen in derselben Quelldatei platzieren. Jeder Datensatz ist in der Objektdatei in der gleichen Reihenfolge enthalten, in der er in der Quelldatei auftritt.

Wenn die Reihenfolge der Standardbibliothek und einer hinzugefügten Bibliothek wichtig ist, verhindert die Kompilierung mit dem Schalter [/Zl](../build/reference/zl-omit-default-library-name.md) , dass der Standard Bibliotheksname im Objekt Modul platziert wird. Ein zweites comment-Pragma kann dann verwendet werden, um den Namen der Standardbibliothek nach der hinzugefügten Bibliothek einzufügen. Die Bibliotheken, die mit diesen Pragmas aufgelistet werden, werden im Objektmodul in derselben Reihenfolge angezeigt, wie sie sich im Quellcode befinden.

### <a name="linker"></a>Linker

Platziert eine [Linkeroption](../build/reference/linker-options.md) in der Objektdatei. Sie können diesen Kommentartyp verwenden, um eine Linkeroption anzugeben, statt sie an die Befehlszeile zu übergeben oder in der Entwicklungsumgebung anzugeben. Beispielsweise können Sie die /include-Option angeben, um das Einfügen eines Symbols zu erzwingen:

```C
#pragma comment(linker, "/include:__mySymbol")
```

Es können nur die folgenden Linkeroptionen (*comment-Type*) an den Linker-Bezeichner übermittelt werden:

- [/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)

- [/EXPORT](../build/reference/export-exports-a-function.md)

- [/INCLUDE](../build/reference/include-force-symbol-references.md)

- [/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)

- [/MERGE](../build/reference/merge-combine-sections.md)

- [/SECTION](../build/reference/section-specify-section-attributes.md)

### <a name="user"></a>Benutzer

Platziert einen allgemeinen Kommentar in der Objektdatei. Der *comment-String-* Parameter enthält den Text des Kommentars. Dieser Kommentardatensatz wird vom Linker ignoriert.

## <a name="examples"></a>Beispiele

Das folgende Pragma bewirkt, dass der Linker während der Verknüpfung nach der EMAPI.LIB-Bibliothek sucht. Der Linker sucht zunächst im aktuellen Arbeitsverzeichnis und anschließend im Pfad, der in der LIB-Umgebungsvariablen angegeben wird.

```C
#pragma comment( lib, "emapi" )
```

Das folgende Pragma bewirkt, dass der Compiler den Namen und die Versionsnummer des Compilers in die Objektdatei platziert:

```C
#pragma comment( compiler )
```

Bei Kommentaren, die einen *Kommentar Zeichenfolgen-* Parameter verwenden, können Sie ein Makro an einer beliebigen Stelle verwenden, an der Sie ein Zeichenfolgenliteralzeichen verwenden würden Sie können auch jede beliebige Kombination aus Zeichenfolgenliteralen und Makros verketten, die als Zeichenfolgenliterale erweitert werden. Beispielsweise ist die folgende Anweisung akzeptabel.

```C
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

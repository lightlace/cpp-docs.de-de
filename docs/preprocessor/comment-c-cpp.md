---
title: Kommentar (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.comment
- comment_CPP
dev_langs:
- C++
helpviewer_keywords:
- annotations [C++]
- comments [C++], compiled files
- pragmas, comment
- comment pragma
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30683bb76ce674becb81321607bc95fefdb78ac1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="comment-cc"></a>comment (C/C++)
Platziert einen Kommentardatensatz in einer Objektdatei oder ausführbaren Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die *Kommentartyp* ist eine vordefinierte Bezeichner, die unten beschriebenen, der den Typ des Kommentardatensatzes angibt. Das optionale Zeichenfolgenliteral `commentstring` bietet zusätzliche Informationen für einige Kommentartypen. Da `commentstring` ist ein Zeichenfolgenliteral ist, entspricht es allen Regeln für Zeichenfolgenliterale in Zusammenhang mit Escapezeichen, eingebetteten Anführungszeichen (**"**), und Verkettung.  
  
 **compiler**  
 Platziert den Namen und die Versionsnummer des Compilers in der Objektdatei. Dieser Kommentardatensatz wird vom Linker ignoriert. Wenn Sie einen `commentstring`-Parameter für diesen Datensatztyp angeben, generiert der Compiler eine Warnung.  
  
 **exestr**  
 Platziert `commentstring` in der Objektdatei. Zum Zeitpunkt der Verknüpfung wird diese Zeichenfolge in der ausführbaren Datei platziert. Die Zeichenfolge wird nicht in den Arbeitsspeicher geladen, wenn die ausführbare Datei geladen wird. Allerdings kann sie mit einem Programm gesucht werden, das druckbare Zeichenfolgen in Dateien sucht. Eine Verwendung für diesen comment-record-Typ ist, eine Versionsnummer oder ähnliche Informationen in einer ausführbaren Datei einzubetten.  
  
 `exestr` ist veraltet und wird in einer der nächsten Versionen entfernt. Der Linker verarbeitet den Kommentardatensatz nicht.  
  
 **lib**  
 Platziert einen einen Datensatz für Bibliothekssuchvorgänge in der Objektdatei. Dieser Kommentartyp muss von einem `commentstring`-Parameter begleitet werden, der den Namen (und ggf. den Pfad) der Bibliothek enthält, den der Linker suchen soll. Der Bibliotheksname folgt den Standard-bibliothekssuchvorgängen in der Objektdatei; der Linker sucht nach dieser Bibliothek, als ob Sie es in der Befehlszeile genannt hätten, vorausgesetzt, dass die Bibliothek nicht angegeben ist, mit [/NODEFAULTLIB](../build/reference/nodefaultlib-ignore-libraries.md). Sie können mehrere Datensätze an Bibliothekssuchvorgängen in derselben Quelldatei platzieren. Jeder Datensatz ist in der Objektdatei in der gleichen Reihenfolge enthalten, in der er in der Quelldatei auftritt.  
  
 Wenn die Reihenfolge der Standardbibliothek und einer hinzugefügten Bibliothek wichtig ist, kompilieren Sie mit der [Zl](../build/reference/zl-omit-default-library-name.md) Switch wird verhindert, dass der Standardname der Bibliothek, die in das Objektmodul platziert wird. Ein zweites comment-Pragma kann dann verwendet werden, um den Namen der Standardbibliothek nach der hinzugefügten Bibliothek einzufügen. Die Bibliotheken, die mit diesen Pragmas aufgelistet werden, werden im Objektmodul in derselben Reihenfolge angezeigt, wie sie sich im Quellcode befinden.  
  
 **linker**  
 Stellen ein [Linkeroption](../build/reference/linker-options.md) in der Objektdatei. Sie können diesen Kommentartyp verwenden, um eine Linkeroption anzugeben, statt sie an die Befehlszeile zu übergeben oder in der Entwicklungsumgebung anzugeben. Beispielsweise können Sie die /include-Option angeben, um das Einfügen eines Symbols zu erzwingen:  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 Nur die folgenden (*Kommentartyp*) stehen Linkeroptionen können dem linkerbezeichner übergeben werden:  
  
-   [/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [/EXPORT](../build/reference/export-exports-a-function.md)  
  
-   [/ INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [/ MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [/ ' MERGE '](../build/reference/merge-combine-sections.md)  
  
-   [/ SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **user**  
 Platziert einen allgemeinen Kommentar in der Objektdatei. Der `commentstring`-Parameter enthält den Text des Kommentars. Dieser Kommentardatensatz wird vom Linker ignoriert.  
  
 Das folgende Pragma bewirkt, dass der Linker während der Verknüpfung nach der EMAPI.LIB-Bibliothek sucht. Der Linker sucht zunächst im aktuellen Arbeitsverzeichnis und anschließend im Pfad, der in der LIB-Umgebungsvariablen angegeben wird.  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 Das folgende Pragma bewirkt, dass der Compiler den Namen und die Versionsnummer des Compilers in die Objektdatei platziert:  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  Für Kommentare, die einen `commentstring`-Parameter akzeptieren, können Sie ein Makro in einem beliebigen Ort verwenden, an dem Sie ein Zeichenfolgenliteral verwenden würden, vorausgesetzt, dass das Makro sich zu einem Zeichenfolgenliteral erstreckt. Sie können auch jede beliebige Kombination aus Zeichenfolgenliteralen und Makros verketten, die als Zeichenfolgenliterale erweitert werden. Beispielsweise ist die folgende Anweisung akzeptabel.  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
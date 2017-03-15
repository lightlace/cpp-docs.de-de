---
title: "comment (C/C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.comment"
  - "comment_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Anmerkungen [C++]"
  - "comment-Pragma"
  - "Kommentare [C++], Kompilierte Dateien"
  - "Pragmas, comment"
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# comment (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Platziert einen Kommentardatensatz in einer Objektdatei oder ausführbaren Datei.  
  
## Syntax  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## Hinweise  
 Der *comment\-type* ist einer der vordefinierten, unten beschriebenen Bezeichner, der den Typ des Kommentardatensatzes angibt.  Das optionale Zeichenfolgenliteral `commentstring` bietet zusätzliche Informationen für einige Kommentartypen.  Da `commentstring` ein Zeichenfolgenliteral ist, entspricht es allen Regeln für Zeichenfolgenliterale in Zusammenhang mit Escapezeichen, eingebetteten Anführungszeichen \(**"**\) und Verkettungen.  
  
 **compiler**  
 Platziert den Namen und die Versionsnummer des Compilers in der Objektdatei.  Dieser Kommentardatensatz wird vom Linker ignoriert.  Wenn Sie einen `commentstring`\-Parameter für diesen Datensatztyp angeben, generiert der Compiler eine Warnung.  
  
 **exestr**  
 Platziert `commentstring` in der Objektdatei.  Zum Zeitpunkt der Verknüpfung wird diese Zeichenfolge in der ausführbaren Datei platziert.  Die Zeichenfolge wird nicht in den Arbeitsspeicher geladen, wenn die ausführbare Datei geladen wird. Allerdings kann sie mit einem Programm gesucht werden, das druckbare Zeichenfolgen in Dateien sucht.  Eine Verwendung für diesen comment\-record\-Typ ist, eine Versionsnummer oder ähnliche Informationen in einer ausführbaren Datei einzubetten.  
  
 `exestr` ist veraltet und wird in einer der nächsten Versionen entfernt. Der Linker verarbeitet den Kommentardatensatz nicht.  
  
 **lib**  
 Platziert einen einen Datensatz für Bibliothekssuchvorgänge in der Objektdatei.  Dieser Kommentartyp muss von einem `commentstring`\-Parameter begleitet werden, der den Namen \(und ggf. den Pfad\) der Bibliothek enthält, den der Linker suchen soll.  Der Bibliotheksname folgt den Standardbibliothekssucheinträgen in der Objektdatei; der Linker sucht nach dieser Bibliothek, so als ob Sie diese auf der Befehlszeile genannt hätten, unter der Voraussetzung, dass die Bibliothek nicht mit [\/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md) bezeichnet ist.  Sie können mehrere Datensätze an Bibliothekssuchvorgängen in derselben Quelldatei platzieren. Jeder Datensatz ist in der Objektdatei in der gleichen Reihenfolge enthalten, in der er in der Quelldatei auftritt.  
  
 Wenn die Reihenfolge der Standardbibliothek und einer hinzugefügten Bibliothek wichtig ist, verhindert die Kompilierung mit dem Schalter [\/Zl](../build/reference/zl-omit-default-library-name.md), dass der Name der Standardbibliothek in das Objektmodul übernommen wird.  Ein zweites comment\-Pragma kann dann verwendet werden, um den Namen der Standardbibliothek nach der hinzugefügten Bibliothek einzufügen.  Die Bibliotheken, die mit diesen Pragmas aufgelistet werden, werden im Objektmodul in derselben Reihenfolge angezeigt, wie sie sich im Quellcode befinden.  
  
 **Linker**  
 Platziert eine [Linkeroption](../build/reference/linker-options.md) in der Objektdatei.  Sie können diesen Kommentartyp verwenden, um eine Linkeroption anzugeben, statt sie an die Befehlszeile zu übergeben oder in der Entwicklungsumgebung anzugeben.  Beispielsweise können Sie die \/include\-Option angeben, um das Einfügen eines Symbols zu erzwingen:  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 Nur die folgenden \(*comment\-type*\) Linkeroptionen können dem Linkerbezeichner übergeben werden:  
  
-   [\/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [\/EXPORT](../build/reference/export-exports-a-function.md)  
  
-   [\/INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [\/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [\/MERGE](../build/reference/merge-combine-sections.md)  
  
-   [\/SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **Benutzer**  
 Platziert einen allgemeinen Kommentar in der Objektdatei.  Der `commentstring`\-Parameter enthält den Text des Kommentars.  Dieser Kommentardatensatz wird vom Linker ignoriert.  
  
 Das folgende Pragma bewirkt, dass der Linker während der Verknüpfung nach der EMAPI.LIB\-Bibliothek sucht.  Der Linker sucht zunächst im aktuellen Arbeitsverzeichnis und anschließend im Pfad, der in der LIB\-Umgebungsvariablen angegeben wird.  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 Das folgende Pragma bewirkt, dass der Compiler den Namen und die Versionsnummer des Compilers in die Objektdatei platziert:  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  Für Kommentare, die einen `commentstring`\-Parameter akzeptieren, können Sie ein Makro in einem beliebigen Ort verwenden, an dem Sie ein Zeichenfolgenliteral verwenden würden, vorausgesetzt, dass das Makro sich zu einem Zeichenfolgenliteral erstreckt.  Sie können auch jede beliebige Kombination aus Zeichenfolgenliteralen und Makros verketten, die als Zeichenfolgenliterale erweitert werden.  Beispielsweise ist die folgende Anweisung akzeptabel.  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
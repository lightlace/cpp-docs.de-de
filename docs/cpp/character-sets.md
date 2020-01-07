---
title: Token und Zeichensätze
ms.date: 12/10/2019
helpviewer_keywords:
- Tokens (C++)
- Character sets
- basic source character set (C++)
- universal character names
- basic execution character set (C++)
ms.assetid: 379a2af6-6422-425f-8352-ef0bca6c0d74
ms.openlocfilehash: 1f6dbe2faa6348d61ec00b411cc35e8ef5ceb57a
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301612"
---
# <a name="tokens-and-character-sets"></a>Token und Zeichensätze

Der Text eines C++ Programms besteht aus Token und *Leerzeichen*. Ein Token ist das kleinste Element eines C++-Programms, das für den Compiler von Bedeutung ist. Der C++ Parser erkennt folgende Arten von Token:

- [Stichwörter](../cpp/keywords-cpp.md)
- [Bezeichner](../cpp/identifiers-cpp.md)
- [Numerische, boolesche und Zeigerliterale](../cpp/numeric-boolean-and-pointer-literals-cpp.md)
- [Zeichenfolgen- und Zeichenliterale](../cpp/string-and-character-literals-cpp.md)
- [Benutzerdefinierte Literale](../cpp/user-defined-literals-cpp.md)
- [Operatoren](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
- [Markierungszeichen](../cpp/punctuators-cpp.md)

Token werden normalerweise durch *Leerzeichen*getrennt, wobei es sich um eine oder mehrere handeln kann:

- Leerzeichen
- Horizontale oder vertikale Tabstopps
- Zeilenumbrüche
- Formular Feeds
- Comments

## <a name="basic-source-character-set"></a>Einfacher Quellzeichensatz

Der C++ Standard gibt einen *einfachen Quell Zeichensatz* an, der in Quelldateien verwendet werden kann. Es können zusätzliche Zeichen mithilfe eines *universellen Zeichennamens*angegeben werden, um Zeichen außerhalb dieses Satzes darzustellen. Die MSVC-Implementierung lässt zusätzliche Zeichen zu. Der *grundlegende Quell Zeichensatz* besteht aus 96 Zeichen, die in Quelldateien verwendet werden können. Dieser Satz umfasst das Leerzeichen, den horizontalen Tabstopp, den vertikalen Tabstopp, die Steuerzeichen für Seitenvorschub und Zeilenwechsel sowie diese Gruppe von Grafikzeichen:

`a b c d e f g h i j k l m n o p q r s t u v w x y z`

`A B C D E F G H I J K L M N O P Q R S T U V W X Y Z`

`0 1 2 3 4 5 6 7 8 9`

`_ { } [ ] # ( ) < > % : ; . ? * + - / ^ & | ~ ! = , \ " '`

**Microsoft-spezifisch**

MSVC enthält das `$` Zeichen als Member des grundlegenden Quell Zeichensatzes. MSVC ermöglicht außerdem die Verwendung eines zusätzlichen Satzes von Zeichen in Quelldateien, basierend auf der Datei Codierung. Standardmäßig speichert Visual Studio die Quelldateien mithilfe der Standardcodepage. Wenn Quelldateien mit einer Gebiets Schema spezifischen Codepage oder einer Unicode-Codepage gespeichert werden, können Sie mithilfe von MSVC beliebige Zeichen dieser Codepage in Ihrem Quellcode verwenden, mit Ausnahme der Steuercodes, die im einfachen Quell Zeichensatz nicht explizit zulässig sind. Beispielsweise können Sie japanische Zeichen in Kommentaren, Bezeichnern oder Zeichenfolgenliteralen einfügen, wenn Sie die Datei mit einer japanischen Codepage speichern. MSVC lässt keine Zeichen folgen zu, die in gültige Multibytezeichen oder Unicode-Code Punkte übersetzt werden können. In Abhängigkeit von den Compileroptionen werden möglicherweise nicht alle zulässigen Zeichen in Bezeichnern angezeigt. Weitere Informationen finden Sie unter [Identifiers](../cpp/identifiers-cpp.md).

**Ende Microsoft-spezifisch**

### <a name="universal-character-names"></a>Universelle Zeichennamen

Da C++-Programme mehr Zeichen als die im einfachen Quellzeichensatz angegebenen Zeichen verwenden können, können Sie diese Zeichen mithilfe *universeller Zeichennamen*auf portierbare Weise angeben. Ein universeller Zeichennamen besteht aus einer Folge von Zeichen, die einen Unicode-Codepunkt darstellen.  Diese nehmen zwei Formen an. Verwenden Sie `\UNNNNNNNN` , um einen Unicode-Codepunkt der Form „U+NNNNNNNN“ darzustellen, wobei „NNNNNNNN“ die achtstellige hexadezimale Codepunktnummer angibt. Verwenden Sie das vierstellige `\uNNNN` , um einen Unicode-Codepunkt in der Form U+0000NNNN darzustellen.

Universelle Zeichennamen können in Bezeichnern und Zeichenfolgen sowie in Zeichenliteralen verwendet werden. Ein universeller Zeichennamen kann nicht dazu verwendet werden, um einen Ersatzcodepunkt im Bereich 0xD800-0xDFFF darzustellen. Verwenden Sie stattdessen den gewünschten Codepunkt. Der Compiler generiert automatisch alle erforderlichen Ersatzzeichen. Zusätzliche Einschränkungen gelten für die universellen Zeichennamen, die in Bezeichnern verwendet werden können. Weitere Informationen finden Sie unter [Identifiers](../cpp/identifiers-cpp.md) und [String and Character Literals](../cpp/string-and-character-literals-cpp.md).

**Microsoft-spezifisch**

Der Microsoft C++ -Compiler behandelt ein Zeichen in Form eines universellen Zeichen namens und in literalform austauschbar. Sie können z. B. einen Bezeichner in Form eines universellen Zeichennamens deklarieren und ihn dann in Literalform verwenden:

```cpp
auto \u30AD = 42; // \u30AD is 'キ'
if (キ == 42) return true; // \u30AD and キ are the same to the compiler
```

Das Format von Sonderzeichen in der Windows-Zwischenablage ist von den Gebietsschemaeinstellungen der Anwendung abhängig. Das Ausschneiden und Einfügen dieser Zeichen in Ihren Code aus einer anderen Anwendung kann zu unerwarteten Zeichencodierungen führen. Dies kann in Ihrem Code ohne ersichtlichen Grund zu Analysefehlern führen. Es wird empfohlen, dass Sie für Ihre Quelldateicodierung eine Unicode-Codepage festlegen, bevor Sie Sonderzeichen einfügen. Außerdem wird empfohlen, dass Sie einen Eingabemethoden-Editor oder eine App zur Zeichenzuordnung verwenden, um Sonderzeichen zu generieren.

**Ende Microsoft-spezifisch**

### <a name="execution-character-sets"></a>Ausführungs Zeichensätze

Die *Ausführungs Zeichensätze* stellen die Zeichen und Zeichen folgen dar, die in einem kompilierten Programm vorkommen können. Diese Zeichensätze bestehen aus allen Zeichen, die in einer Quelldatei zulässig sind, sowie aus den Steuerzeichen, die Warnung, Rücktaste, Wagen Rücklauf und NULL-Zeichen darstellen. Der Ausführungszeichensatz weist eine gebietsschemaspezifische Darstellung auf.

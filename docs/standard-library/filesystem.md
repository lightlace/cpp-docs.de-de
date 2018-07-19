---
title: '&lt;filesystem&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::recursive_directory_iterator
- filesystem/std::experimental::filesystem::path
- filesystem/std::experimental::filesystem::filesystem_error
- filesystem/std::experimental::filesystem::directory_iterator
- <filesystem>
dev_langs:
- C++
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c85c19e4f23f7c6e9454793ac86a574614ec2fae
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847246"
---
# <a name="ltfilesystemgt"></a>&lt;filesystem&gt;

Verwenden Sie den Header &lt;filesystem>, um auf Klassen und Funktion zuzugreifen, die Informationen über Pfade, Dateien und Verzeichnisse ändern und abrufen.

## <a name="syntax"></a>Syntax

```cpp
#include <experimental/filesystem> // C++-standard header file name
#include <filesystem> // Microsoft-specific implementation header file name
using namespace std::experimental::filesystem::v1;
```

> [!IMPORTANT]
> Ab der Version von Visual Studio 2017 die \<Filesystem >-Header wurde noch keinem C++-Standard. Visual C++ 2017 implementiert den endgültigen Entwurfsstandard aus [ISO/IEC JTC 1/SC 22/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf).

Dieser Header unterstützt Dateisysteme für eine von zwei umfangreichen Klassen von Hostbetriebssystemen: Microsoft Windows und POSIX.

Der überwiegende Teil der Funktionalität ist für beide Betriebssysteme gleich. In diesem Dokuments sind die Unterschiede aufgeführt. Zum Beispiel:

- Windows unterstützt mehrere Stammnamen, z.B. „c:“ oder „\\\Netzwerkname“. Ein Dateisystem besteht aus einer Gesamtheit von Strukturen, von denen jede ein eigenes Stammverzeichnis, z.B. „c:\“ oder „\\\Netzwerkname\\“, und ein eigenes aktuelles Verzeichnis hat, um einen relativen Pfadnamen (ein Pfadname, der kein absoluter Pfadnamen ist) zu komplettieren.

- POSIX unterstützt eine einzige Struktur, ohne Stammnamen, das einzige Stammverzeichnis / und ein einziges aktuelles Verzeichnis.

Ein weiterer wichtiger Unterschied ist die systemeigene Darstellung von Pfadnamen:

- Windows verwendet eine nullterminierte Sequenz von wchar_t-Zeichen, die als UTF-16 codiert sind (ein oder zwei Elemente für jedes Zeichen).

- POSIX verwendet eine nullterminierte von char-Zeichen, die als UTF-8 codiert sind (ein oder mehrere Elemente für jedes Zeichen).

- Ein Objekt eines Klassenpfads speichert den Pfadnamen im systemeigenen Format, unterstützt aber einfache Konvertierung zwischen dieser gespeicherten Form und mehreren externen Formen:

- Eine nullterminierte Sequenz von char-Zeichen, die entsprechend der Vorgabe des Betriebssystems codiert sind

- Eine nullterminierte Sequenz von char-Zeichen, die als UTF-8 codiert sind

- Eine nullterminierte Sequenz von wchar_t-Zeichen, die entsprechend der Vorgabe des Betriebssystems codiert sind

- Eine nullterminierte Sequenz von char16_t-Zeichen, die als UTF-16 codiert sind

- Eine nullterminierte Sequenz von char32_t-Zeichen, die als UTF-32 codiert sind

Gegenseitige Konvertierungen zwischen diesen Darstellungen werden nach Bedarf dadurch vermittelt, dass mindestens ein `codecvt`-Facet verwendet wird. Wenn ein bestimmtes Gebietsschemaobjekt nicht festgelegt ist, werden dieser Facets aus dem globalen Gebietsschema abgerufen.

Ein weiterer Unterschied ist das Detail, über das das jeweilige Betriebssystem Ihnen die Möglichkeit gibt, Datei- oder Verzeichniszugriffsberechtigungen anzugeben:

1. Windows protokolliert, ob eine Datei schreibgeschützt ist oder schreibbar ist. Dies ist ein Attribut, das für Verzeichnisse keine Bedeutung hat.

1. POSIX protokolliert, ob eine Datei vom Besitzer, von der Gruppe des Besitzers oder von jedem gelesen , geschrieben oder ausgeführt (durchsucht, wenn Verzeichnis) werden kann, und protokolliert einige andere Berechtigungen.

Beiden Systemen gemeinsam ist die Struktur, die für einen Pfadnamen gilt, sobald Sie über den Stammnamen hinausgelangen. Für den Pathnamen „c:/abc/xyz/def.ext“ gilt:

- Der Stammname ist „c:“.

- Das Stammverzeichnis ist /.

- Der Stammpfad ist „c:/“.

- Der relative Pfad ist „abc/xyz/def.ext“.

- Der übergeordnete Pfad ist „c:/abc/xyz“.

- Der Dateiname ist „def.ext“.

- Der Stamm ist „def“.

- Die Erweiterung ist „.ext“.

Ein geringfügiger Unterschied ist das **bevorzugte Trennzeichen**, das zwischen der Sequenz von Verzeichnissen in einem Pfadnamen verwendet wird. In beiden Betriebssysteme können Sie einen Schrägstrich (/) schreiben, aber in bestimmten Kontexten bevorzugt Windows einen umgekehrten Schrägstrich (\\).

Eine wichtige Funktion von Pfadobjekten ist schließlich, dass Sie diese überall dort verwenden können, wo ein Argument namens „filename“ in den Klassen erforderlich ist, die im Header \<fstream> definiert sind.

Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation (C++)](../standard-library/file-system-navigation.md).

## <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[directory_entry-Klasse](../standard-library/directory-entry-class.md)|Beschreibt ein Objekt, das von einem `directory_iterator` oder einem `recursive_directory_iterator` zurückgegeben wird und einen Pfad enthält|
|[directory_iterator-Klasse.](../standard-library/directory-iterator-class.md)|Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Dateisystemverzeichnis durchläuft.|
|[filesystem_error-Klasse](../standard-library/filesystem-error-class.md)|Eine Basisklasse für Ausnahmen, die ausgelöst werden, um einen Systemüberlauf auf niedriger Ebene zu melden.|
|[path-Klasse](../standard-library/path-class.md)|Definiert eine Klasse, die ein für die Verwendung als Dateiname geeignetes Objekt des Vorlagentyps `String` speichert.|
|[recursive_directory_iterator-Klasse](../standard-library/recursive-directory-iterator-class.md)|Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Dateisystemverzeichnis durchläuft. Der Iterator kann die Verzeichnisse auch absteigend anordnen.|
|[file_status-Klasse](../standard-library/file-status-class.md)|Bricht ein `file_type`um.|

## <a name="structs"></a>Strukturen

|name|Beschreibung|
|----------|-----------------|
|[space_info-Struktur](../standard-library/space-info-structure.md)|Enthält Informationen zu einem Volume.|

## <a name="functions"></a>Funktionen

[\<filesystem> Funktionen](../standard-library/filesystem-functions.md)

## <a name="operators"></a>Operatoren

[\<filesystem>-Operatoren](../standard-library/filesystem-operators.md)

## <a name="enumerations"></a>Enumerationen

|name|Beschreibung|
|----------|-----------------|
|[copy_options](../standard-library/filesystem-enumerations.md#copy_options)|Eine mit [copy_file](http://msdn.microsoft.com/4af7a9b0-8861-45ed-b84e-0307f0669d60) verwendete Enumeration, mit der das Verhalten bestimmt wird, wenn eine Datei vorhanden ist.|
|[directory_options](../standard-library/filesystem-enumerations.md#directory_options)|Eine Enumeration, die Optionen für Verzeichnisiteratoren angibt.|
|[file_type](../standard-library/filesystem-enumerations.md#file_type)|Eine Enumeration für Dateitypen.|
|[perms](../standard-library/filesystem-enumerations.md#perms)|Ein Bitmaskentyp, mit dem Berechtigungen und Optionen zu Berechtigungen übermittelt werden.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>

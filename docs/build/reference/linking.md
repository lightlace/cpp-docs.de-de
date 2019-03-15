---
title: MSVC-Linker-Referenz
ms.date: 12/10/2018
ms.assetid: bb736587-d13b-4f3c-8982-3cc2c015c59c
ms.openlocfilehash: 3a9eebef0a264b0131311b5ca96011a4d56264a1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820376"
---
# <a name="linking"></a>Verknüpfen

In einem C++-Projekt die *verknüpfen* Schritt wird ausgeführt, nachdem der Compiler den Quellcode in Objektdateien (*.obj) kompiliert wurde. Der Linker (link.exe) kombiniert die Objektdateien in einer einzelnen ausführbaren Datei. 

Optionen des Linkers können innerhalb oder außerhalb von Visual Studio festgelegt werden. Innerhalb von Visual Studio können Sie Optionen des Linkers zugreifen, indem Sie mit der rechten Maustaste auf einen Projektknoten **Projektmappen-Explorer** und **Eigenschaften** die Eigenschaftenseiten angezeigt. Wählen Sie **Linker** im linken Bereich auf den Knoten erweitern und alle Optionen angezeigt. 


## <a name="linker-command-line-syntax"></a>Syntax für die Linkerbefehlszeile

Wenn Sie den LINK außerhalb von Visual Studio ausführen, können Sie die Eingabe auf einen oder mehrere Arten angeben:

- Über die Befehlszeile

- Verwenden von Befehlsdateien

- In Umgebungsvariablen

LINK zuerst Prozesse angegebenen Optionen in der LINK-Umgebungsvariablen, gefolgt von den Optionen in der Reihenfolge, die sie in der Befehlszeile angegeben sind und in Befehlsdateien. Wenn Sie eine Option mit verschiedenen Argumenten wiederholt wird, hat der letzte Suchvorgang verarbeitet Vorrang vor.

Optionen gelten für die gesamte Build; keine Optionen können für bestimmte Eingabedateien angewendet werden.

LINK zum Ausführen. EXE-Datei, verwenden Sie die folgende Befehlssyntax:

```
LINK arguments
```

Die `arguments` umfassen Optionen und Dateinamen ein, und können in beliebiger Reihenfolge angegeben werden. Optionen werden zuerst verarbeitet, und klicken Sie dann auf Dateien. Verwenden Sie eine oder mehrere Leerzeichen oder Tabstopps, um Argumente zu trennen.

> [!NOTE]
>  Sie können dieses Tool nur über die Visual Studio-Eingabeaufforderung starten. Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei-Explorer aus starten.

## <a name="command-line"></a>Befehlszeile

In der Befehlszeile eine Option besteht aus einem Optionsbezeichner, entweder einen Bindestrich (-) oder einem Schrägstrich (/), gefolgt von den Namen der Option. Optionsnamen können nicht abgekürzt werden. Einige Optionen haben ein Argument, das nach einem Doppelpunkt (:) angegeben. Keine Leerzeichen oder Tabstopps sind innerhalb einer Optionsangabe, außer in eine Zeichenfolge in Anführungszeichen in der Option "/ Comment" zulässig. Geben Sie numerische Argumente, in Dezimalstellen oder C-Notation. Optionsnamen und ihren Argumenten-Schlüsselwort oder einen Dateinamen sind keine Groß-/Kleinschreibung beachtet, aber bestehenden Argumenten wird Groß-/Kleinschreibung beachtet.

Um eine Datei an dem Linker übergeben werden soll, geben Sie den Dateinamen in der Befehlszeile nach dem LINK-Befehl. Sie können einen absoluten oder relativen Pfad angeben, mit dem Dateinamen, und Sie können Platzhalter im Dateinamen verwenden. Wenn Sie den Punkt (.) und die Dateierweiterung weglassen, wird LINK obj für die Suche nach der Datei angenommen. LINK verwendet Dateinamenerweiterungen oder das Fehlen von ihnen keine Annahmen zum Inhalt der Dateien; Bestimmt den Typ der Datei durch Untersuchen und verarbeitet ihn entsprechend.

Link.exe gibt 0 für Erfolg (fehlerfrei) zurück.  Andernfalls der Linker die Fehlernummer, die den Link beendet.  Wenn der Linker LNK1104 generiert wird, gibt der Linker z. B. 1104 zurück.  Entsprechend ist die niedrigste Fehlernummer, die bei einem Fehler zurückgegeben, die vom Linker 1000.  Ein Rückgabewert von 128 stellt ein Konfigurationsproblem mit dem Betriebssystem oder einer .config-Datei dar; das Ladeprogramm link.exe oder c2.dll nicht geladen werden.

## <a name="link-command-files"></a>LINK-Befehlsdateien

Sie können Befehlszeilenargumente an LINK in der Form eine Befehlsdatei übergeben. Um eine Befehlsdatei für den Linker anzugeben, verwenden Sie die folgende Syntax:

> **LINK \@**  <em>Commandfile</em>

Die *Commandfile* ist der Name einer Textdatei. Keine Leerzeichen oder Tabstopp kann zwischen den at-Zeichen (**\@**) sowie den Dateinamen. Es gibt keine standardmäßige Erweiterung. Sie müssen den vollständigen Dateinamen, Einbinden von Erweiterungen angeben. Platzhalter können verwendet werden. Sie können einen absoluten oder relativen Pfad mit dem Dateinamen angeben. LINK wird keine Umgebungsvariable verwendet, um für die Datei zu suchen.

In der Befehlsdatei Argumente können getrennt werden durch Leerzeichen oder Tabulatorzeichen (z. B. auf der Befehlszeile) und durch neue Zeilenumbruchzeichen.

Sie können in einer Befehlsdatei ganz oder teilweise von der Befehlszeile angeben. Sie können mehr als eine Befehlsdatei in einem Linkbefehl verwenden. LINK akzeptiert die Befehlsdatei-Eingaben, als ob es an diesem Speicherort in der Befehlszeile angegeben wurden. Befehlsdateien werden nicht geschachtelt. LINK gibt den Inhalt der Befehlsdateien, es sei denn, die [/nologo](nologo-suppress-startup-banner-linker.md) angegeben wird.

## <a name="example"></a>Beispiel

Der folgende Befehl zum Erstellen einer DLL übergibt die Namen von Objektdateien und Bibliotheken in separaten Befehlsdateien aus, und verwendet eine dritte Datei für die Angabe der Option/Exports-Befehl:

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="link-environment-variables"></a>LINK-Umgebungsvariablen

Das LINK-Tool verwendet die folgenden Umgebungsvariablen:

- LINK und \_LINK\_, wenn definiert. Das LINK-Tool voran, die Optionen und Argumente, die in der Umgebungsvariablen LINK definiert ist, und fügt die Optionen und Argumente definiert, der \_LINK\_ -Umgebungsvariable auf die Argumente über die Befehlszeile vor der Verarbeitung.

- LIB, falls definiert. Der LINK-Tools verwenden den LIB-Pfad an, bei der Suche nach der ein Objekt, Bibliothek oder anderen Datei angegeben, in der Befehlszeile oder durch die [/BASE](base-base-address.md) Option. Der LIB-Pfad wird auch verwendet, um nach einer in einem Objekt genannten PDB-Datei zu suchen. Die LIB-Variable kann mehrere durch Semikolons getrennte Pfadangaben enthalten. Ein Pfad muss auf das Unterverzeichnis \lib der Visual C++-Installation zeigen.

- PATH, wenn das Tool CVTRES ausführen muss und die Datei nicht im selben Verzeichnis wie LINK findet. (LINK benötigt CVTRES, um eine RES-Datei zu verknüpfen.) PATH muss auf das Unterverzeichnis \bin der Visual C++-Installation zeigen.

- TMP zum Angeben eines Verzeichnisses beim Verknüpfen von OMF oder RES-Dateien

## <a name="see-also"></a>Siehe auch

[Referenz zur C/C++-Erstellung](c-cpp-building-reference.md)
[MSVC-Linkeroptionen](linker-options.md)
[Moduldefinitionsdateien (.def)](module-definition-dot-def-files.md)
[Linkerunterstützung für Verzögertes Laden von DLLs](linker-support-for-delay-loaded-dlls.md)

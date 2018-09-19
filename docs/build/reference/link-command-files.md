---
title: LINK-Befehlsdateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2611fc0c16e4ff30d7802989518ca8c5d8dc33af
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713719"
---
# <a name="link-command-files"></a>LINK-Befehlsdateien

Sie können Befehlszeilenargumente an LINK in der Form eine Befehlsdatei übergeben. Um eine Befehlsdatei für den Linker anzugeben, verwenden Sie die folgende Syntax:

> **LINK \@**  <em>Commandfile</em>

Die *Commandfile* ist der Name einer Textdatei. Keine Leerzeichen oder Tabstopp kann zwischen den at-Zeichen (**\@**) sowie den Dateinamen. Es gibt keine standardmäßige Erweiterung. Sie müssen den vollständigen Dateinamen, Einbinden von Erweiterungen angeben. Platzhalter können verwendet werden. Sie können einen absoluten oder relativen Pfad mit dem Dateinamen angeben. LINK wird keine Umgebungsvariable verwendet, um für die Datei zu suchen.

In der Befehlsdatei Argumente können getrennt werden durch Leerzeichen oder Tabulatorzeichen (z. B. auf der Befehlszeile) und durch neue Zeilenumbruchzeichen.

Sie können in einer Befehlsdatei ganz oder teilweise von der Befehlszeile angeben. Sie können mehr als eine Befehlsdatei in einem Linkbefehl verwenden. LINK akzeptiert die Befehlsdatei-Eingaben, als ob es an diesem Speicherort in der Befehlszeile angegeben wurden. Befehlsdateien werden nicht geschachtelt. LINK gibt den Inhalt der Befehlsdateien, es sei denn, die [/nologo](../../build/reference/nologo-suppress-startup-banner-linker.md) angegeben wird.

## <a name="example"></a>Beispiel

Der folgende Befehl zum Erstellen einer DLL übergibt die Namen von Objektdateien und Bibliotheken in separaten Befehlsdateien aus, und verwendet eine dritte Datei für die Angabe der Option/Exports-Befehl:

```cmd
link /dll @objlist.txt @liblist.txt @exports.txt
```

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
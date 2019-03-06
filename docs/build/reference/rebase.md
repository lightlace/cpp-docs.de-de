---
title: /REBASE
ms.date: 11/04/2016
f1_keywords:
- /rebase
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
ms.openlocfilehash: f0b581dfc116e25228a9aa9133c4de027e194799
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422038"
---
# <a name="rebase"></a>/REBASE

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>Hinweise

Diese Option wird die Basisadressen für den angegebenen Dateien. EDITBIN weist neue Basisadressen in einem zusammenhängendem Adressraum entsprechend der Größe der einzelnen Dateien, aufgerundet auf die nächsten 64 KB. Weitere Informationen über die Basisadressen, finden Sie unter den [Basisadresse](../../build/reference/base-base-address.md) (/ BASE)-Linkeroption.

Angeben des Programms ausführbare Dateien und DLLs in den *Dateien* Argument in der EDITBIN-Befehlszeile in der Reihenfolge, in denen sie basieren soll sind. Sie können optional angeben, eine oder mehrere *Modifizierer*und jeweils durch ein Komma getrennt (**,**):

|Modifizierer|Aktion|
|--------------|------------|
|**BASE=**<em>address</em>|Enthält eine Startadresse für erneutes Zuweisen von Basisadressen zu den Dateien an. Geben Sie *Adresse* in Dezimal oder C-Notation. Wenn Basis nicht angegeben ist, wird der standardmäßigen Start-Basisadresse 0 x 400000. Wenn Sie verwendet, Basis wird muss angegeben werden, und *Adresse* wird das Ende des Bereichs von Basisadressen.|
|**BASEFILE**|Erstellt eine Datei mit dem Namen COFFBASE. TXT, das ist eine Textdatei in das Format des Links/Basis-Option.|
|**NACH UNTEN**|Teilt EDITBIN für die neuzuweisung der Basisadressen von-Endadresse an. Die Dateien werden in der Reihenfolge angegeben werden, wobei die erste Datei befindet sich in der höchstmöglichen Adresse nach dem Ende des Adressbereichs neu zugewiesen. Basis muss mit der Sie verwendet werden, um sicherzustellen, dass genügend Adressraum für Basisadressen. Um zu bestimmen, den Adressraum, der von den angegebenen Dateien benötigt, führen Sie EDITBIN mit REBASE aus, auf die Dateien aus, und fügen 64 KB angezeigten Gesamtgröße hinzu.|

## <a name="see-also"></a>Siehe auch

[EDITBIN-Optionen](../../build/reference/editbin-options.md)

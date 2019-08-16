---
title: /ALLOWISOLATION (Manifestsuche)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: 7c799f3d44428643bccc2869255ffa4e9d194d70
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493133"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Manifestsuche)

Gibt das Verhalten bei der Manifestsuche an.

## <a name="syntax"></a>Syntax

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Hinweise

**/ALLOWISOLATION: No** gibt an, dass DLLs geladen werden, als ob kein Manifest vorhanden wäre, und bewirkt `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` , dass der Linker das Bit `DllCharacteristics` im Feld des optionalen Headers festgelegt hat.

**/ALLOWISOLATION** bewirkt, dass das Betriebssystem Manifeste suchen und lädt.

**/ALLOWISOLATION** ist die Standardeinstellung.

Wenn die Isolation für eine ausführbare Datei deaktiviert ist, wird vom Windows-Lade Programm nicht versucht, ein Anwendungs Manifest für den neu erstellten Prozess zu finden. Der neue Prozess weist keinen Standard Aktivierungs Kontext auf, selbst wenn ein Manifest in der ausführbaren Datei vorhanden ist oder im gleichen Verzeichnis wie die ausführbare Datei mit dem Namen " <em>ausführbare Datei Name</em> **. exe. Manifest**" platziert wird.

Weitere Informationen finden Sie unter [Manifest-Dateireferenz](/windows/win32/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften** > Seite der > linkermanifestressourcendatei aus.

1. Ändern Sie die Eigenschaft **Isolation zulassen** .

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)

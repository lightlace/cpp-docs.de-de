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
ms.openlocfilehash: 7b2cb4160a0d25aa65d2c5eb345ba1bc08b1c6b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428092"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Manifestsuche)

Gibt das Verhalten bei der Manifestsuche an.

## <a name="syntax"></a>Syntax

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Hinweise

**/ALLOWISOLATION:No** DLLs geladen, als ob es kein Manifest gäbe und bewirkt, dass den Linker an, legen Sie die `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit im des optionalen Headers `DllCharacteristics` Feld.

**/ ALLOWISOLATION** bewirkt, dass das Betriebssystem manifestsuch- und-Ladevorgänge durchführt.

**/ ALLOWISOLATION** ist die Standardeinstellung.

Wenn Isolation für eine ausführbare Datei deaktiviert ist, versucht das Windows-Ladeprogramm nicht um ein Anwendungsmanifest für den neu erstellten Prozess zu finden. Der neue Prozess keinen Standard-Aktivierungskontext, selbst wenn ein Manifest in die ausführbare Datei oder in demselben Verzeichnis wie die ausführbare Datei mit dem Namen aufgenommen werden <em>Name der ausführbaren Datei</em>**. exe.manifest**.

Weitere Informationen finden Sie unter [Manifestdateienreferenz](/windows/desktop/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Manifestdatei** Eigenschaftenseite.

1. Ändern der **Isolation zulassen** Eigenschaft.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)

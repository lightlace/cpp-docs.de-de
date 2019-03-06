---
title: /PROFILE (Leistungstools-Profiler)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: a0fda47497ffc247dd9678ece7aac76291aed1ff
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419152"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Leistungstools-Profiler)

Erstellt eine Ausgabedatei, die mit dem Leistungstoolprofiler verwendet werden kann.

## <a name="syntax"></a>Syntax

```
/PROFILE
```

## <a name="remarks"></a>Hinweise

/ PROFILE impliziert die folgenden Optionen des Linkers:

- [/OPT:REF](../../build/reference/opt-optimizations.md)

- /OPT:NOICF

- [/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md)

- [/FIXED:NO](../../build/reference/fixed-fixed-base-address.md)

/ PROFILE bewirkt, dass der Linker ein Verschiebungsabschnitt im Programmimage generiert.  Umsetzungsabschnitt kann der Profiler die Programm-Images zum Abrufen von Profildaten zu transformieren.

**/ PROFILE** ist nur in Enterprise (Entwicklung im Team)-Versionen verfügbar.  Weitere Informationen zu PREfast finden Sie unter [Codeanalyse für C/C++-Übersicht](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **erweitert** Eigenschaftenseite.

1. Ändern der **Profil** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)

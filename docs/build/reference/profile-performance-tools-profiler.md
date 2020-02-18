---
title: /PROFILE (Leistungstools-Profiler)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 678816ce455d2a982ff8218becd805a0b2cdd896
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416032"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Leistungstools-Profiler)

Erstellt eine Ausgabedatei, die mit dem Leistungstoolprofiler verwendet werden kann.

## <a name="syntax"></a>Syntax

```
/PROFILE
```

## <a name="remarks"></a>Hinweise

/Profile impliziert die folgenden Linkeroptionen:

- [/OPT: Ref](opt-optimizations.md)

- /OPT: NOICF

- [/Incremental: Nein](incremental-link-incrementally.md)

- [/Fixed: Nein](fixed-fixed-base-address.md)

/Profile bewirkt, dass der Linker einen Verschiebungs Abschnitt im Programm Abbild generiert.  Ein Verschiebungs Abschnitt ermöglicht dem Profiler das Transformieren des Programm Images, um Profildaten zu erhalten.

**/Profile** ist nur in der Enterprise-Version (Team Development) verfügbar.  Weitere Informationen zu PREfast finden Sie unter [Code Analyse für C/C++ Overview](/cpp/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie den Knoten **Linker**.

1. Wählen Sie die Eigenschaftenseite **Erweitert** aus.

1. Ändern Sie die **Profil** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>So legen Sie diese Linkeroption innerhalb des Visual Studio cmake-Projekts fest

**Cmake** -Projekt verfügt nicht über eine **Eigenschaften Seite**. die Linkeroptionen können durch Ändern der Datei "CMakeLists. txt" festgelegt werden.

1. Öffnen Sie die Datei "CMakeLists. txt" im Stammverzeichnis des Projekts.

1. Fügen Sie unten Code hinzu. Weitere Informationen finden Sie unter [cmake-Verweise](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html) .

1. Erstellen Sie die Projektmappe neu.

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>Weitere Informationen

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)


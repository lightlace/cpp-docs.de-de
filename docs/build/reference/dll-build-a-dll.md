---
title: /DLL (DLL erstellen)
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: edad85b2890679e4247c7d34b4e19534e871f4dd
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420062"
---
# <a name="dll-build-a-dll"></a>/DLL (DLL erstellen)

```
/DLL
```

## <a name="remarks"></a>Hinweise

Die/DLL-Option erstellt eine DLL als Hauptausgabedatei. Eine DLL-Datei enthält in der Regel die Exporte, die von einem anderen Programm verwendet werden können. Es gibt drei Methoden zum Angeben von Exports, aufgelistet in empfohlener Reihenfolge von Nutzen:

1. [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) im Quellcode

1. Ein [EXPORTE](../../build/reference/exports.md) -Anweisung in DEF-Datei

1. Ein [/EXPORT](../../build/reference/export-exports-a-function.md) Spezifikation in einem LINK-Befehl

Ein Programm kann mehr als eine Methode verwenden.

Eine weitere Möglichkeit zum Erstellen einer DLL wird mit der **Bibliothek** Moduldefinitionsdatei-Anweisung. Die Optionen/Base "und" / DLL zusammen entsprechen den **Bibliothek** Anweisung.

Angegeben Sie diese Option in der Entwicklungsumgebung nicht werden, Diese Option ist für die Verwendung nur in der Befehlszeile. Diese Option wird festgelegt, wenn Sie ein DLL-Projekt mit einer Anwendungs-Assistenten erstellen.

Beachten Sie, dass wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, bevor Sie die DLL-Datei erstellen, den gleichen Satz von Objektdateien müssen beim Erstellen der DLL-Datei übergeben werden wie bei der Erstellung der Importbibliothek.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Konfigurationseigenschaften** Ordner.

1. Klicken Sie auf die **allgemeine** Eigenschaftenseite.

1. Ändern der **Konfigurationstyp** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)

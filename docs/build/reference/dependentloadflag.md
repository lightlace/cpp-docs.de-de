---
title: /DEPENDENTLOADFLAG (abhängige Standardladeflags festlegen)
description: Die Option/DEPENDENTLOADFLAG legt Standard abhängige Auslastungs Flags für DLLs fest, die von diesem Modul geladen werden.
ms.date: 01/22/2020
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 5e31a0d747e7186814cba3ae1c4cf243569d87a8
ms.sourcegitcommit: b67b08472b6f1ee8f1c5684bba7056d3e0fc745f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76725707"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (abhängige Standardladeflags festlegen)

::: moniker range="vs-2015"

Die **/DEPENDENTLOADFLAG** -Option erfordert Visual Studio 2017 oder höher.

::: moniker-end

::: moniker range=">=vs-2017"

Legt die standardauslastungs Flags fest, die verwendet werden, wenn das Betriebssystem die statisch verknüpften Importe eines Moduls auflöst.

## <a name="syntax"></a>Syntax

> **/DEPENDENTLOADFLAG**[ __:__ *load_flags*]

### <a name="arguments"></a>Argumente

*load_flags*<br/>
Ein optionaler ganzzahliger Wert, der die Auslastungs Flags angibt, die beim Auflösen von statisch verknüpften Import Abhängigkeiten des Moduls angewendet werden. Der Standardwert ist 0. Eine Liste der unterstützten Flagwerte finden Sie in den `LOAD_LIBRARY_SEARCH_*` Einträgen in [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw).

## <a name="remarks"></a>Hinweise

Wenn das Betriebssystem die statisch verknüpften Importe eines Moduls auflöst, wird die [Standard Such Reihenfolge](/windows/win32/dlls/dynamic-link-library-search-order)verwendet. Verwenden Sie die Option **/DEPENDENTLOADFLAG** , um einen *load_flags* Wert anzugeben, der den Suchpfad ändert, mit dem diese Importe aufgelöst werden. Auf unterstützten Betriebssystemen wird die Such Reihenfolge für die statische Import Auflösung geändert, ähnlich wie [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) bei der Verwendung `LOAD_LIBRARY_SEARCH` Parameters. Weitere Informationen zu der Such Reihenfolge, die *load_flags*festgelegt ist, finden [Sie unter Search Order using LOAD_LIBRARY_SEARCH Flags](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags).

Dieses Flag kann verwendet werden, um den Vektor eines [dll-anfügenden Angriffs](/windows/win32/dlls/dynamic-link-library-security) erschwert zu gestalten. Nehmen Sie beispielsweise eine APP, die eine DLL statisch verknüpft hat:

- Ein Angreifer könnte eine DLL mit dem gleichen Namen weiter oben im Suchpfad der Import Auflösung, z. b. dem Anwendungsverzeichnis, angleichen. Geschützte Verzeichnisse sind schwieriger, aber nicht unmöglich, damit sich ein Angreifer ändern kann.

- Wenn die dll in der Anwendung,%Windows%\System32 und% Windows%-Verzeichnisse fehlt, wird die Import Auflösung in das aktuelle Verzeichnis überlaufen. Ein Angreifer könnte dort eine DLL-.

Wenn Sie in beiden Fällen die Link-Option `/DEPENDENTLOADFLAG:0x800` (den Wert des Flags `LOAD_LIBRARY_SEARCH_SYSTEM32`) angeben, ist der Suchpfad des Moduls auf das Verzeichnis "%Windows%\System32" beschränkt. Er bietet einen gewissen Schutz vor der Anpflanzung von Angriffen auf die anderen Verzeichnisse. Weitere Informationen finden Sie unter [Dynamic-Link Library Security](/windows/win32/dlls/dynamic-link-library-security).

Um den von der **/DEPENDENTLOADFLAG** -Option in einer beliebigen DLL festgelegten Wert anzuzeigen, verwenden Sie den [DUMPBIN](dumpbin-reference.md) -Befehl mit der [/LOADCONFIG](loadconfig.md) -Option.

Die **/DEPENDENTLOADFLAG** -Option ist neu in Visual Studio 2017. Dies gilt nur für apps, die unter Windows 10, Version und höher ausgeführt werden. Diese Option wird von anderen Betriebssystemen, auf denen die app ausgeführt wird, ignoriert.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die dependentloadflag-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie die **Eigenschaften** Seite für die > **Linker** -> der **Befehlszeile** aus.

1. Geben Sie die Option in **zusätzliche Optionen**ein.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linkerreferenz](linking.md)
- [MSVC (Linkeroptionen)](linker-options.md)
- [Implizites Verknüpfen einer ausführbaren Datei mit einer dll](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Bestimmen der zu verwendenden Verknüpfungs Methode](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Such Reihenfolge der Dynamic Link Library](/windows/win32/Dlls/dynamic-link-library-search-order)
- [Dynamic Link Library-Sicherheit](/windows/win32/dlls/dynamic-link-library-security)

::: moniker-end

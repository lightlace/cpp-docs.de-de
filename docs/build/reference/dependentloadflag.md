---
title: /DEPENDENTLOADFLAG (abhängige Standardladeflags festlegen)
description: Die Option/DEPENDENTLOADFLAG legt Standardflags für DLLs fest, die mit LoadLibrary geladen wurden.
ms.date: 12/22/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 3a403f22c88ccd3e25ba95c183656ad2ffafd05a
ms.sourcegitcommit: ef34a11cb04511221bf5c7b9f4f55ad91a7a603f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2019
ms.locfileid: "75329997"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (abhängige Standardladeflags festlegen)

Legt die standardlastflags fest, die verwendet werden, wenn `LoadLibrary` zum Laden von DLLs verwendet wird.

## <a name="syntax"></a>Syntax

> **/DEPENDENTLOADFLAG**[__:__*load_flags*]

### <a name="arguments"></a>Argumente

*load_flags*<br/>
Ein optionaler 16-Bit-ganzzahliger Wert von 16 Bit in Decimal, oktale mit einer führenden Null oder hexadezimal Zahl mit einer führenden `0x`, die die abhängigen Auslastungs Flags angibt, die auf alle [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) -Aufrufe angewendet werden sollen. Der Standardwert ist 0.

## <a name="remarks"></a>Hinweise

Diese Option ist neu in Visual Studio 2017. Dies gilt nur für apps, die unter Windows 10, Version und höher ausgeführt werden. Diese Option wird von anderen Betriebssystemen, auf denen die app ausgeführt wird, ignoriert.

Bei unterstützten Betriebssystemen wirkt sich diese Option auf das Ändern von Aufrufen von `LoadLibrary("dependent.dll")` in die Entsprechung von `LoadLibraryEx("dependent.dll", 0, load_flags)`aus. Aufrufe von [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) sind nicht betroffen. Diese Option gilt nicht rekursiv für DLLs, die von ihrer App geladen werden.

Dieses Flag kann verwendet werden, um die [dll-anfügende Angriffe](/windows/win32/dlls/dynamic-link-library-security) zu erschweren. Wenn eine APP beispielsweise `LoadLibrary` zum Laden einer abhängigen DLL verwendet, könnte ein Angreifer eine DLL mit dem gleichen Namen in dem Suchpfad, der von `LoadLibrary`verwendet wird, z. b. dem aktuellen Verzeichnis, verwenden, das möglicherweise vor Systemverzeichnissen geprüft wird, wenn der sichere DLL-Suchmodus deaktiviert ist. Der sichere DLL-Suchmodus speichert das aktuelle Verzeichnis des Benutzers später in der Such Reihenfolge und ist in Windows XP SP2 und höheren Versionen standardmäßig aktiviert. Weitere Informationen finden Sie unter [Dynamic-Link Library Search Order](/windows/win32/Dlls/dynamic-link-library-search-order).

Wenn Sie die Link-Option `/DEPENDENTLOADFLAG:0xA00` angeben (der Wert der kombinierten Flags `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), und auch wenn der sichere DLL-Suchmodus auf dem Computer des Benutzers deaktiviert ist, ist der dll-Suchpfad auf das Anwendungsverzeichnis beschränkt, gefolgt vom Verzeichnis%Windows%\System32. Eine `/DEPENDENTLOADFLAG:0x800` Option ist noch restriktiver und schränkt die Suche auf das Verzeichnis "%Windows%\System32" ein. Geschützte Verzeichnisse sind schwieriger, aber nicht unmöglich, damit sich ein Angreifer ändern kann. Informationen zu den verfügbaren Flags und ihren symbolischen und numerischen Werten finden Sie in der Beschreibung des *dwFlags* -Parameters in [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw). Informationen zur Such Reihenfolge, die verwendet wird, wenn verschiedene abhängige Load-Flags verwendet werden, finden [Sie unter Search Order using LOAD_LIBRARY_SEARCH Flags](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die dependentloadflag-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **Linker** > **Befehlszeile**.

1. Geben Sie die Option in **zusätzliche Optionen**ein.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linkerreferenz](linking.md)
- [MSVC-Linkeroptionen](linker-options.md)
- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Link an executable to a DLL (Eine ausführbare Datei mit einer DLL verknüpfen)](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [Such Reihenfolge der Dynamic Link Library](/windows/win32/Dlls/dynamic-link-library-search-order)

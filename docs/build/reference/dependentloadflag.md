---
title: /DEPENDENTLOADFLAG (abhängige Standardladeflags festlegen)
description: Die Option/DEPENDENTLOADFLAG legt Standardflags für DLLs fest, die mit LoadLibrary geladen wurden.
ms.date: 05/18/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 072fa1103d049c7d5c395ae88d268f3b47e20b4f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492954"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (abhängige Standardladeflags festlegen)

Legt die standardlastflags fest `LoadLibrary` , die verwendet werden, wenn zum Laden von DLLs verwendet wird

## <a name="syntax"></a>Syntax

> **/DEPENDENTLOADFLAG** [ **:** _loadflags_]

### <a name="arguments"></a>Argumente

*loadflags*<br/>
Ein optionaler 16-Bit-ganzzahliger Wert mit einer Länge von 16 Bit in Decimal, oktale mit einer führenden Null oder hexadezimal Zahl mit einer führenden `0x`, die die abhängigen Auslastungs Flags angibt, die auf alle [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) -Aufrufe angewendet werden sollen. Der Standardwert ist 0.

## <a name="remarks"></a>Hinweise

Diese Option ist neu in Visual Studio 2017 und gilt nur für apps, die unter Windows 10 RS1 und höheren Versionen ausgeführt werden. Diese Option wird von anderen Betriebssystemen, auf denen die app ausgeführt wird, ignoriert.

Auf unterstützten Betriebssystemen hat diese Option die Auswirkung, dass Aufrufe `LoadLibrary("dependent.dll")` von in die-Entsprechung von `LoadLibraryEx("dependent.dll", 0, loadflags)`geändert werden. Aufrufe von [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) sind nicht betroffen. Diese Option gilt nicht rekursiv für DLLs, die von ihrer App geladen werden.

Dieses Flag kann verwendet werden, um dll-anfügende Angriffe zu verhindern. Wenn eine APP beispielsweise verwendet `LoadLibrary` , um eine abhängige DLL zu laden, könnte ein Angreifer eine DLL mit dem gleichen Namen in dem Suchpfad, der von `LoadLibrary`verwendet wird, wie z. b. dem aktuellen Verzeichnis,, der vor Systemverzeichnissen geprüft werden kann, wenn der sichere DLL-Suchmodus ist deaktiviert. Der sichere DLL-Suchmodus speichert das aktuelle Verzeichnis des Benutzers später in der Such Reihenfolge und ist in Windows XP SP2 und höheren Versionen standardmäßig aktiviert. Weitere Informationen finden Sie unter [Dynamic-Link Library Search Order](/windows/win32/Dlls/dynamic-link-library-search-order).

Wenn Sie die Link-Option `/DEPENDENTLOADFLAG:0xA00` (den Wert der kombinierten Flags `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`) angeben und der Such Modus der sicheren dll auf dem Computer des Benutzers deaktiviert ist, ist der dll-Suchpfad auf geschützte Verzeichnisse beschränkt, die für einen Angreifer schwieriger zu Klima. Informationen zu den verfügbaren Flags und ihren symbolischen und numerischen Werten finden Sie in der Beschreibung des *dwFlags* -Parameters in [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die dependentloadflag-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1.  > Wählen Sie die Eigenschaften Seite für die Linkerbefehlszeile der **Configuration Properties** > 

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

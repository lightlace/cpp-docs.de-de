---
title: /ZW (Windows-Runtime-Kompilierung)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: a16482cf8d21651db9486ab19c347a4ccadf5279
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809430"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows-Runtime-Kompilierung)

Kompiliert Quellcode zur Unterstützung von Visual C++-komponentenerweiterungen C++ / CX für die Erstellung von apps für universelle Windows-Plattform (UWP).

Bei Verwendung von **/Zw** zum Kompilieren, geben Sie immer **/EHsc** ebenfalls.

## <a name="syntax"></a>Syntax

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>Argumente

**nostdlib**<br/>
Gibt an, dass Platform.winmd, Windows.Foundation.winmd und andere Standard-Windows-Metadatendateien (.winmd) nicht automatisch in die Kompilierung eingeschlossen werden. Sie müssen stattdessen die [/FU (Name Forced #using using-Datei)](fu-name-forced-hash-using-file.md) -Compileroption verwenden, um explizit Windows-Metadatendateien angeben.

## <a name="remarks"></a>Hinweise

Bei Angabe der **/Zw** der Compiler-Option unterstützt diese Features:

- Die erforderlichen Metadatendateien, Namespaces, Datentypen und Funktionen, die Ihre app benötigt, um in der Windows-Runtime auszuführen.

- Automatische referenzzählung von Windows-Runtime-Objekte und Automatisches Verwerfen eines Objekts, wenn dessen Verweiszähler auf Null geht.

Da der incremental Linker die Windows-Metadaten in OBJ-Dateien enthalten sind, mithilfe von nicht unterstützt. die **/Zw** -Option der [/GM (minimale Neuerstellung aktivieren)](gm-enable-minimal-rebuild.md) inkompatibel mit  **/Zw**.

Weitere Informationen finden Sie unter [Sprachreferenz zu Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).

## <a name="requirements"></a>Anforderungen

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)

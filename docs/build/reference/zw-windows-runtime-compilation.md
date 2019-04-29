---
title: /ZW (Windows-Runtime-Kompilierung)
ms.date: 04/08/2019
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
ms.openlocfilehash: 73295866004fd506fd5f06ff25c048d14b821016
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315312"
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

Da der incremental Linker die Windows-Metadaten in OBJ-Dateien enthalten sind, mithilfe von nicht unterstützt. die **/Zw** option, die als veraltet markierten [/GM (minimale Neuerstellung aktivieren)](gm-enable-minimal-rebuild.md) inkompatibel mit **/Zw**.

Weitere Informationen finden Sie unter [Sprachreferenz zu Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).

## <a name="requirements"></a>Anforderungen

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)

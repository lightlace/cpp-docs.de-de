---
title: .OBJ-Dateien als Linkereingabe
ms.date: 12/29/2017
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.openlocfilehash: 36f41077fcba6b093865625d426b8009f6185e7b
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450577"
---
# <a name="obj-files-as-linker-input"></a>.OBJ-Dateien als Linkereingabe

Der Linker-Tool (LINK. EXE-Datei) akzeptiert OBJ-Dateien, die im Common Object File Format (COFF).

## <a name="remarks"></a>Hinweise

Microsoft bietet eine vollständige Beschreibung des allgemeinen Objekts-Dateiformats ab. Weitere Informationen finden Sie unter [PE-Format](/windows/desktop/Debug/pe-format).

## <a name="unicode-support"></a>Unterstützung für Unicode

Visual Studio 2005 ab, der Microsoft-MSVC-Compiler wird Unicode-Zeichen in Bezeichnern gemäß ISO/IEC C- und C++-Standards unterstützt. Frühere Versionen des Compilers unterstützt nur ASCII-Zeichen in Bezeichnern. Verwenden zur Unterstützung von Unicode in die Namen der Funktionen, Klassen und statische Variablen Compiler und Linker die Unicode UTF-8-Codierung für COFF-Symbole in OBJ-Dateien. UTF-8-Codierung ist kompatibel mit der ASCII-Codierung, die von früheren Versionen von Visual Studio verwendet.

Weitere Informationen zu den Compiler und Linker finden Sie unter [Unicode-Unterstützung im Compiler und Linker](unicode-support-in-the-compiler-and-linker.md). Weitere Informationen zu den Unicode-Standard, finden Sie unter den [Unicode](https://www.unicode.org/) Organisation.

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](link-input-files.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[Unterstützung für Unicode](../../text/support-for-unicode.md)<br/>
[Unicode-Unterstützung im Compiler und Linker](unicode-support-in-the-compiler-and-linker.md)<br/>
[Unicode-standard](https://www.unicode.org/)<br/>
[PE-Format](/windows/desktop/Debug/pe-format)

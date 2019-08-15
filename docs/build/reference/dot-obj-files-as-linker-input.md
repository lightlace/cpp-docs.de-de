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
ms.openlocfilehash: 3e02ccc09ae8c9c2f3df88bc1767ff0188baa1f4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492940"
---
# <a name="obj-files-as-linker-input"></a>.OBJ-Dateien als Linkereingabe

Das Linker-Tool (Link. EXE) akzeptiert OBJ-Dateien im Common Object File Format (COFF).

## <a name="remarks"></a>Hinweise

Microsoft stellt eine umfassende Beschreibung des Common Object File Format bereit. Weitere Informationen finden Sie unter [PE-Format](/windows/win32/Debug/pe-format).

## <a name="unicode-support"></a>Unterstützung für Unicode

Ab Visual Studio 2005 unterstützt der Microsoft MSVC-Compiler Unicode-Zeichen in Bezeichners gemäß ISO/IEC c-und- C++ Standards. In früheren Versionen des Compilers wurden nur ASCII-Zeichen in Bezeichnerzeichen unterstützt. Zur Unterstützung von Unicode in den Namen von Funktionen, Klassen und Statics verwenden der Compiler und Linker die Unicode-UTF-8-Codierung für COFF-Symbole in OBJ-Dateien. Die UTF-8-Codierung ist aufwärts kompatibel mit der ASCII-Codierung, die von früheren Versionen von Visual Studio verwendet wurde.

Weitere Informationen zum Compiler und zum Linker finden Sie [unter Unicode-Unterstützung im Compiler und Linker](unicode-support-in-the-compiler-and-linker.md). Weitere Informationen zum Unicode-Standard finden Sie unter [Unicode](https://www.unicode.org/) -Organisation.

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](link-input-files.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)<br/>
[Unterstützung für Unicode](../../text/support-for-unicode.md)<br/>
[Unicode-Unterstützung im Compiler und Linker](unicode-support-in-the-compiler-and-linker.md)<br/>
[Unicode-Standard](https://www.unicode.org/)<br/>
[PE-Format](/windows/win32/Debug/pe-format)

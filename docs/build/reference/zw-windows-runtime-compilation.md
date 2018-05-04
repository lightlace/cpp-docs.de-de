---
title: -ZW (Windows-Runtime-Kompilierung) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs:
- C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fce6c6825ed4ae715a2f4cde6b0e1ffa8b3b6733
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows-Runtime-Kompilierung)
Kompiliert Quellcode zur Unterstützung von [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) für die Erstellung von apps der universellen Windows-Plattform (UWP).  
  
 Bei Verwendung von **/Zw** zum Kompilieren, geben Sie immer **/EHsc /** ebenfalls.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
/ZW /EHsc  
/ZW:nostdlib /EHsc  
```  
  
## <a name="arguments"></a>Argumente  
 nostdlib  
 Gibt an, dass Platform.winmd, Windows.Foundation.winmd und andere Standard-Windows-Metadatendateien (.winmd) nicht automatisch in die Kompilierung eingeschlossen werden. Stattdessen müssen Sie verwenden die [/FU (Name Forced #using-Datei)](../../build/reference/fu-name-forced-hash-using-file.md) Compileroption, um die Windows-Metadatendateien explizit angeben.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie bei der **/Zw** Option den Compiler unterstützt diese Funktionen:  
  
-   Die erforderlichen Metadatendateien, Namespaces, Datentypen und Funktionen, die Ihre app benötigt, um im Windows-Runtime ausgeführt werden.  
  
-   Automatische referenzzählung von Windows-Runtime-Objekte, und Automatisches Verwerfen eines Objekts, wenn der Verweiszähler auf 0 (null) ist.  
  
 Da der Linker inkrementelle nicht die Windows-Metadaten in der OBJ-Dateien mithilfe von eingeschlossen unterstützt die **/Zw** -Option der [/GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) -Option ist nicht kompatibel mit  **/Zw**.  
  
 Weitere Informationen finden Sie unter [Sprachreferenz zu Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).  
  
## <a name="requirements"></a>Anforderungen  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
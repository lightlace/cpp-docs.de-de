---
title: -ZW (Windows-Runtime-Kompilierung) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs: C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4af8070518cbb35d2f005fd255675ab4fb334b38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows-Runtime-Kompilierung)
Kompiliert Quellcode zur Unterstützung von [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) für die Erstellung von [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]-Apps.  
  
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
  
 Da der Linker inkrementelle nicht die Windows-Metadaten in der OBJ-Dateien mithilfe von eingeschlossen unterstützt die **/Zw** -Option der [/GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) -Option ist nicht kompatibel mit   **/Zw** .  
  
 Weitere Informationen finden Sie unter [Sprachreferenz zu Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).  
  
## <a name="requirements"></a>Anforderungen  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
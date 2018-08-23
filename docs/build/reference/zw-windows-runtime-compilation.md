---
title: -ZW (Windows-Runtime-Kompilierung) | Microsoft-Dokumentation
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
ms.openlocfilehash: 97a97158dda886a09fb6ccb00898a8c518d8e250
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602261"
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
 nostdlib  
 Gibt an, dass Platform.winmd, Windows.Foundation.winmd und andere Standard-Windows-Metadatendateien (.winmd) nicht automatisch in die Kompilierung eingeschlossen werden. Sie müssen stattdessen die [/FU (Name Forced #using using-Datei)](../../build/reference/fu-name-forced-hash-using-file.md) -Compileroption verwenden, um explizit Windows-Metadatendateien angeben.  
  
## <a name="remarks"></a>Hinweise  
 Bei Angabe der **/Zw** der Compiler-Option unterstützt diese Features:  
  
-   Die erforderlichen Metadatendateien, Namespaces, Datentypen und Funktionen, die Ihre app benötigt, um in der Windows-Runtime auszuführen.  
  
-   Automatische referenzzählung von Windows-Runtime-Objekte und Automatisches Verwerfen eines Objekts, wenn dessen Verweiszähler auf Null geht.  
  
 Da der incremental Linker die Windows-Metadaten in OBJ-Dateien enthalten sind, mithilfe von nicht unterstützt. die **/Zw** -Option der [/GM (minimale Neuerstellung aktivieren)](../../build/reference/gm-enable-minimal-rebuild.md) inkompatibel mit  **/Zw**.  
  
 Weitere Informationen finden Sie unter [Sprachreferenz zu Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).  
  
## <a name="requirements"></a>Anforderungen  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
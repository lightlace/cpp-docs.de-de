---
title: '-Zc: Wchar_t (Wchar_t ist der systemeigene Typ) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3375e39120fdc8f2b0d8d5502aa6def997511ff5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t ist der systemeigene Typ)
Analysieren Sie `wchar_t` als integrierten Typ entsprechend dem C++-Standard. Standardmäßig **/Zc: wchar_t** befindet sich auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zc:wchar_t[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn **/Zc: wchar_t** aktiviert ist, `wchar_t` ordnet die Microsoft-spezifischen systemeigenen Typ `__wchar_t`. Wenn **/Zc:wchar_t-** (mit einem Minuszeichen) angegeben wird, `wchar_t` ordnet eine `typedef` für `unsigned short`. (In Visual C++ 6.0 und früher wurde `wchar_t` nicht als integrierter Typ implementiert, sondern in wchar.h als `typedef` für `unsigned short` deklariert.) Wir empfehlen nicht **/Zc:wchar_t-** , da die C++-Standard, die erfordert `wchar_t` ein integrierter Typ sein. Die Verwendung der `typedef`-Version kann Portabilitätsprobleme verursachen. Wenn Sie ein von früheren Versionen von Visual C++ Upgrade und Compilerfehler auftreten, [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) , da der Code versucht, eine implizite Konvertierung einer `wchar_t` auf `unsigned short`, es wird empfohlen, dass Sie den Code, um den Fehler zu beheben, stattdessen ändern Einstellung **/Zc:wchar_t-**.  
  
 Microsoft implementiert `wchar_t` als 2-Byte-Wert ohne Vorzeichen. Weitere Informationen zu `wchar_t`, finden Sie unter [Datentypbereiche](../../cpp/data-type-ranges.md) und [grundlegende Typen](../../cpp/fundamental-types-cpp.md).  
  
 Wenn Sie neuen Code schreiben, der mit älterem Code zusammenwirken, die noch verwendet die `typedef` Version `wchar_t`, können Sie für beide Überladungen Bereitstellen der `unsigned short` und `__wchar_t` Variationen des `wchar_t`, sodass der Code mit der verknüpft werden kann mit Code kompiliert **/Zc: wchar_t** oder Code kompiliert, ohne ihn. Andernfalls müssen Sie zwei verschiedene builds der Bibliothek bereitstellen – mit und ohne **/Zc: wchar_t** aktiviert. Allerdings wird in beiden Fällen empfohlen, den älteren und den neuen Code mit demselben Compiler zu erstellen. Kombinieren Sie niemals die Binärdateien, die mit unterschiedlichen Compilern erstellt wurden.  
  
 Wenn **/Zc: wchar_t** angegeben wird, **_WCHAR_T_DEFINED** und **_NATIVE_WCHAR_T_DEFINED** Symbole definiert sind. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md).  
  
 Wenn Ihr Code die globalen Compiler-COM-Funktionen verwendet, da **/Zc: wchar_t** ist jetzt auf standardmäßig, es wird empfohlen, dass Sie explizite Verweise auf comsupp.lib – Ändern der [comment-Pragma](../../preprocessor/comment-c-cpp.md) oder zum Befehl "" Zeile – entweder "comsuppw.lib" oder "comsuppwd.lib". (Muss beim Kompilieren mit **/Zc:wchar_t-**, verwenden Sie "comsupp.lib".) Wenn Sie die comdef.h-Headerdatei einfügen, wird die richtige Bibliothek für Sie angegeben. Weitere Informationen zur Compiler-COM-Unterstützung finden Sie unter [Compiler COM unterstützt](../../cpp/compiler-com-support.md).  
  
 Der Typ `wchar_t` wird nicht unterstützt, wenn Sie C-Code kompilieren. Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [nicht standardmäßigem Verhalten](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie im linken Bereich **Konfigurationseigenschaften**, **C/C++-**, und wählen Sie dann **Sprache**.  
  
3.  Ändern der **Wchar_t als integrierten Typ behandeln** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)
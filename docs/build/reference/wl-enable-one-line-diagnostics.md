---
title: -WL (einzeilige-Diagnostik aktivieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /wl
dev_langs:
- C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58a6b41e66f7ec37ad02747edb8331049b9baef5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376786"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (Einzeilige Diagnostik aktivieren)
Fügt zusätzliche Informationen zu einer Warnung oder Fehlermeldung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/WL  
```  
  
## <a name="remarks"></a>Hinweise  
 Fehler- und Warnmeldungen aus dem C++-Compiler können zusätzliche Informationen folgen, die standardmäßig in einer neuen Zeile angezeigt wird. Wenn Sie über die Befehlszeile kompilieren, kann die zusätzliche Zeile mit Informationen zu der Warnung oder Fehlermeldung angefügt werden. Dies möglicherweise wünschenswert, wenn Sie die Buildausgabe in einer Protokolldatei erfassen und Verarbeiten dieses Protokoll, um alle Fehler und Warnungen zu suchen. Ein Semikolon wird die Fehlermeldung oder Warnung von der zusätzliche Zeile getrennt werden.  
  
 Nicht alle Fehler und Warnungen werden gemeldet haben eine zusätzliche Zeile der Informationen. Im folgende Code wird ein Fehler generiert, der eine zusätzliche Zeile Informationen verfügt; Damit können Sie die Auswirkungen zu testen, bei der Verwendung **/WL**.  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
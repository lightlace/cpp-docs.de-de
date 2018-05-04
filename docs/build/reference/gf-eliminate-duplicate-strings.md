---
title: -GF (Doppelte Zeichenfolgen beseitigen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
dev_langs:
- C++
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e2710fe8c5cc444d9e2681620f6813312a1d65a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Doppelte Zeichenfolgen beseitigen)
Kann der Compiler eine einzige Kopie identischer Zeichenfolgen während der Ausführung im Programmabbild und im Arbeitsspeicher zu erstellen. Dies ist eine Optimierung namens *Stringpooling* kleinere Programme erstellen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GF  
```  
  
## <a name="remarks"></a>Hinweise  
 Bei Verwendung von **/GF**, das Betriebssystem wird nicht die Zeichenfolgenteil des Arbeitsspeichers austauschen und können die Zeichenfolgen zurück, aus der Image-Datei gelesen.  
  
 **/ GF** Zeichenfolgen als nur-Lese pools. Wenn Sie versuchen, die Zeichenfolgen unter Ändern **/GF**, tritt ein Fehler auf.  
  
 Stringpooling kann als mehrere Verweise auf mehrere Puffer beabsichtigt waren mehrere Zeiger auf einen einzelnen Puffer sein. Im folgenden Code `s` und `t` mit derselben Zeichenfolge initialisiert werden. Stringpooling bewirkt, dass sie den gleichen Arbeitsspeicher auf:  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  Die [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) -Option zum Bearbeiten und fortfahren, setzt automatisch das **/GF** Option.  
  
> [!NOTE]
>  Die **/GF** -Compileroption erstellt einen adressierbaren Abschnitt für jede eindeutige Zeichenfolge. Und standardmäßig kann eine Objektdatei bis zu 65.536 adressierbare Abschnitte enthalten. Wenn das Programm mehr als 65.536 Zeichenfolgen enthält, verwenden Sie die [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) Compileroption, um weitere Abschnitte zu erstellen.  
  
 **/ GF** ist wirksam, wenn [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder **/O2** verwendet wird.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.  
  
4.  Ändern der **Stringpooling aktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
---
title: -Link (Optionen an Linker übergeben) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /link
dev_langs:
- C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5b22e21022162a0f9f75e41e3e0bfdce348947e1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373292"
---
# <a name="link-pass-options-to-linker"></a>/link (Optionen an Linker übergeben)
Übergibt eine oder mehrere Optionen des Linkers an den Linker.  
  
## <a name="syntax"></a>Syntax  
  
```  
/link linkeroptions  
```  
  
## <a name="arguments"></a>Argumente  
 `linkeroptions`  
 Die Linkeroption oder Optionen an, an den Linker übergeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Die **/link** Option und die Optionen des Linkers müssen nach allen Dateinamen und CL-Optionen angezeigt werden. Ein Leerzeichen ist erforderlich, zwischen **/link** und `linkeroptions`. Weitere Informationen finden Sie unter [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf eine Linker-Eigenschaftenseite.  
  
4.  Eine oder mehrere Eigenschaften zu ändern.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Diese Compileroption kann programmgesteuert geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
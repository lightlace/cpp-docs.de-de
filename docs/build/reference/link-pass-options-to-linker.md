---
title: "-Link (Optionen an Linker übergeben) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /link
dev_langs: C++
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6732f5a2b144172939e23af4addb37b7605de11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
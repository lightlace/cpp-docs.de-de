---
title: "Anweisungen für den Präprozessor | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: adc6251e-cf6b-4508-bdbb-55f446c838d3
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e5d4790cccc280a6a2d23a66c6959fd07bdefa9b
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="directives-to-the-preprocessor"></a>Anweisungen für den Präprozessor
„Anweisungen“ weisen den C-Präprozessor an, eine bestimmte Aktion für den Text des Programms vor der Kompilierung auszuführen. [Präprozessordirektiven](../preprocessor/preprocessor-directives.md) sind vollständig in *Präprozessorverweis* beschrieben. In diesem Beispiel wird die `#define`-Präprozessordirektive verwendet:  
  
```  
#define MAX 100  
```  
  
 Diese Anweisung weist den Compiler an, vor der Kompilierung jedes Vorkommen von `MAX` durch `100` zu ersetzen. Die Präprozessordirektiven des C-Compilers sind:  
  
|#define|#endif|#ifdef|#line|  
|--------------|-------------|-------------|------------|  
|`#elif`|`#error`|**#ifndef**|**#pragma**|  
|`#else`|`#if`|`#include`|`#undef`|  
  
## <a name="see-also"></a>Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)

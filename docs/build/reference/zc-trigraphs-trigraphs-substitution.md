---
title: '-Zc: Trigraphs (Trigraphen-Ersetzung) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 739e772c87c937a552e07a32fa5bb80b1a1e2508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Trigraphen-Ersetzung)
Wenn **/Zc: trigraphs** angegeben ist, wird der Compiler eine Folge von Zeichen Trigraph mit einem entsprechenden Interpunktionszeichen ersetzt. Geben Sie zum Deaktivieren von Trigraphen-Ersetzung **/Zc:trigraphs-**. Standardmäßig **/Zc: trigraphs** ist deaktiviert.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Zc:trigraphs[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Trigraph besteht aus zwei aufeinander folgenden Fragezeichen (??) gefolgt von einem eindeutigen dritten Zeichen. Beispielsweise ersetzt der Compiler die "?? = "Trigraph mit dem Zeichen"#". Verwenden Sie Trigraphen in C-Quelldateien, die einen Zeichensatz aufweisen, der für einige Interpunktionszeichen keine passenden grafischen Darstellungen enthält.  
  
 Eine Liste der C/C++-Trigraphen, und ein Beispiel, das zeigt, wie Trigraphen verwendet, finden Sie unter [Trigraphen](../../c-language/trigraphs.md).  
  
## <a name="see-also"></a>Siehe auch  
 [/ Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)   
 [Trigraphen](../../c-language/trigraphs.md)
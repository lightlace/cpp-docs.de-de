---
title: Linkertoolfehler Lnk2039 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2039
dev_langs:
- C++
helpviewer_keywords:
- LNK2039
ms.assetid: eaa296bd-4901-41f6-8410-6d03ee827144
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 441765d85ce65a80102ed94b3f4394ae48c0e29f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2039"></a>Linkertoolfehler LNK2039
Importieren von Verweisklasse\<Typ >' in another.obj definiert ist; es sollten entweder importierten oder definiert werden, jedoch nicht beides  
  
 Die Verweisklasse ' <`type`>' wurde in der angegebenen OBJ-Datei importiert, aber auch in einer anderen OBJ-Datei definiert ist. Diese Bedingung kann Laufzeitfehler oder anderes unerwartetes Verhalten verursachen.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie, ob "`type`" in der OBJ-Datei definiert sein, und überprüfen Sie, ob er aus der winmd-Datei importiert werden muss.  
  
2.  Entfernen Sie die Definition oder den Import.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)   
 [Linkertoolfehler LNK1332](../../error-messages/tool-errors/linker-tools-error-lnk1332.md)
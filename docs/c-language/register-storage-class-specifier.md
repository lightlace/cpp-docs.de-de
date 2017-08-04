---
title: "Speicherklassenspezifizierer „register“ | Microsoft-Dokumentation"
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
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 9804516a890ff7a58f0eefb70fb85fa3264c93c4
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="register-storage-class-specifier"></a>Speicherklassenspezifizierer "register"
**Microsoft-spezifisch**  
  
 Der Microsoft C/C++-Compiler berücksichtigt keine Benutzeranforderungen für Registervariablen. Aus Gründen der Portabilität wird jedoch jede andere Semantik, die dem **register**-Schlüsselwort zugeordnet ist, vom Compiler berücksichtigt. Sie können z.B. weder den unären Operator „address-of“ (**&**) auf ein register-Objekt anwenden, noch kann das **register**-Schlüsselwort für Arrays verwendet werden.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md)

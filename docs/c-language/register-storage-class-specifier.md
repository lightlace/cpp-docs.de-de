---
title: Speicherklassenspezifizierer „register“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 211f623923286e598f495920bcbdac3a9321b13a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="register-storage-class-specifier"></a>Speicherklassenspezifizierer "register"
**Microsoft-spezifisch**  
  
 Der Microsoft C/C++-Compiler berücksichtigt keine Benutzeranforderungen für Registervariablen. Aus Gründen der Portabilität wird jedoch jede andere Semantik, die dem **register**-Schlüsselwort zugeordnet ist, vom Compiler berücksichtigt. Sie können z.B. weder den unären Operator „address-of“ (**&**) auf ein register-Objekt anwenden, noch kann das **register**-Schlüsselwort für Arrays verwendet werden.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
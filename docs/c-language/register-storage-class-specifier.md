---
title: "Speicherklassenspezifizierer „register“ | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 95c06471b7d8ea60754c29a9bde3159174e9c194
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="register-storage-class-specifier"></a>Speicherklassenspezifizierer "register"
**Microsoft-spezifisch**  
  
 Der Microsoft C/C++-Compiler berücksichtigt keine Benutzeranforderungen für Registervariablen. Aus Gründen der Portabilität wird jedoch jede andere Semantik, die dem **register**-Schlüsselwort zugeordnet ist, vom Compiler berücksichtigt. Sie können z.B. weder den unären Operator „address-of“ (**&**) auf ein register-Objekt anwenden, noch kann das **register**-Schlüsselwort für Arrays verwendet werden.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
---
title: Speicherklassenspezifizierer "register"
ms.date: 11/04/2016
helpviewer_keywords:
- register variables
- register storage class
ms.assetid: 7577bf48-88ec-4191-873c-ef4217a4034e
ms.openlocfilehash: 339a96e33e186ddcc0615f89ff68a7f87b0bfdc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668649"
---
# <a name="register-storage-class-specifier"></a>Speicherklassenspezifizierer "register"

**Microsoft-spezifisch**

Der Microsoft C/C++-Compiler berücksichtigt keine Benutzeranforderungen für Registervariablen. Aus Gründen der Portabilität wird jedoch jede andere Semantik, die dem **register**-Schlüsselwort zugeordnet ist, vom Compiler berücksichtigt. Sie können z.B. weder den unären Operator „address-of“ (**&**) auf ein register-Objekt anwenden, noch kann das **register**-Schlüsselwort für Arrays verwendet werden.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md)
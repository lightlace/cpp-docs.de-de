---
title: stdext-Namespace | Microsoft-Dokumentation
ms.custom: 
ms.date: 09/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: stdext
dev_langs: C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59da07c0cea58e9fc4b544b9f3bad937b2951f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="stdext-namespace"></a>stdext-Namespace

Mitglieder der [ \<Hash_map >](../standard-library/hash-map.md) und [ \<Hash_set >](../standard-library/hash-set.md) -Headerdateien sind nicht Teil des ISO C++-Standards. Daher wurden diese Typen und Member aus dem `std` -Namespace in den `stdext`-Namespace verschoben, um dem C++-Standard zu entsprechen.

Beim Kompilieren mit ["/ Ze"](../build/reference/za-ze-disable-language-extensions.md), dies ist die Standardeinstellung der Compiler warnt für die Verwendung von `std` für Mitglieder der \<Hash_map > und \<Hash_set > Headerdateien. Verwenden Sie das [warning](../preprocessor/warning.md) -Pragma, um die Warnung zu deaktivieren.

Damit den Compiler generiert einen Fehler für die Verwendung von `std` für Mitglieder der \<Hash_map > und \<Hash_set > Headerdateien mit **"/ Ze"**, fügen Sie die folgende Direktive vor `#include` beliebiger Headerdateien der C++-Standardbibliothek.

```cpp  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  

Beim Kompilieren mit **"/ Za"**, generiert der Compiler einen Fehler.  

## <a name="see-also"></a>Siehe auch

[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)


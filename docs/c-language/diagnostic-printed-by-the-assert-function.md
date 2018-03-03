---
title: Diagnose von der Assert-Funktion gedruckt | Microsoft-Dokumentation
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
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 243956f1d85b07b5d5b810ebfd112b2cbfe16242
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Diagnose von der assert-Funktion gedruckt
**ANSI 4.2** Die von der **assert**-Funktion ausgegebene Diagnose und das Abbruchverhalten dieser Funktion  
  
 Die **assert**-Funktion gibt eine Diagnosemeldung aus und ruft die **abort**-Routine auf, wenn der Ausdruck „false“ (0) ist. Die Diagnosemeldung hat die Form  
  
 **Assertionsfehler**: *Ausdruck***, Datei** *Dateiname***, Zeile** *Zeilennummer*  
  
 wobei der "Dateiname" der Name der Quelldatei und "Zeilennummer" die Zeilennummer der Assertion ist, die in der Quelldatei einen Fehler aufweist. Es werden keine Aktionen ausgeführt, wenn der Ausdruck "true" ist (nicht Null).  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
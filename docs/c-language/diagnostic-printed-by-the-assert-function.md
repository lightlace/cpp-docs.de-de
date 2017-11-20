---
title: Diagnose von der Assert-Funktion gedruckt | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d6e5ea4e5f8bae3fda190ac7a7136035aea0c948
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Diagnose von der assert-Funktion gedruckt
**ANSI 4.2** Die von der **assert**-Funktion ausgegebene Diagnose und das Abbruchverhalten dieser Funktion  
  
 Die **assert**-Funktion gibt eine Diagnosemeldung aus und ruft die **abort**-Routine auf, wenn der Ausdruck „false“ (0) ist. Die Diagnosemeldung hat die Form  
  
 **Assertionsfehler**: *Ausdruck***, Datei** *Dateiname***, Zeile** *Zeilennummer*  
  
 wobei der "Dateiname" der Name der Quelldatei und "Zeilennummer" die Zeilennummer der Assertion ist, die in der Quelldatei einen Fehler aufweist. Es werden keine Aktionen ausgeführt, wenn der Ausdruck "true" ist (nicht Null).  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
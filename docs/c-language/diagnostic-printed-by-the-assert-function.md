---
title: Diagnose von der Assert-Funktion gedruckt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 78b64200-520d-40da-9a61-71553f411d4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e824e94f79aa01ab3a82675fb3e8f76059c567d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43195551"
---
# <a name="diagnostic-printed-by-the-assert-function"></a>Diagnose von der assert-Funktion gedruckt
**ANSI 4.2** Die von der **assert**-Funktion ausgegebene Diagnose und das Abbruchverhalten dieser Funktion  
  
Die **assert**-Funktion gibt eine Diagnosemeldung aus und ruft die **abort**-Routine auf, wenn der Ausdruck „false“ (0) ist. Die Diagnosemeldung hat die Form  

> **Assertionsfehler**: <em>Ausdruck</em>**, Datei** <em>Dateiname</em>**, Zeile** *Zeilennummer*  

Dabei steht *filename* für den Namen der Quelldatei und *linenumber* für die Zeilennummer der Assertion, die in der Quelldatei einen Fehler aufweist. Es werden keine Aktionen ausgeführt, wenn der *Ausdruck* TRUE ist (ungleich Null).  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
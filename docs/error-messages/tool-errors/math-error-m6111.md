---
title: Mathematischer Fehler M6111 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6111
dev_langs: C++
helpviewer_keywords: M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 204df0df4855fd2628a96ac326dd39c0d65151e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6111"></a>Mathematischer Fehler M6111
Stapelunterlauf  
  
 Ein Gleitkomma Vorgang verursachte einen Stapelunterlauf 8087/287/387-Coprozessor oder -Emulator.  
  
 Dieser Fehler wird häufig durch einen Aufruf verursacht eine `long double` Funktion, die keinen Wert zurückgibt. Die folgenden generiert z. B. diesen Fehler bei der Kompilierung und Ausführung:  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 Programm mit Exitcode 139 beendet wird.
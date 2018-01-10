---
title: Funktionen ohne Prototyp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 574c4564394e251dde9345d3658304019dae838d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="unprototyped-functions"></a>Funktionen ohne Prototyp
Für Funktionen, die nicht vollständig Prototyp wird der Aufrufer ganzzahlige Werte als ganze Zahlen und Gleitkommawerte mit doppelter Genauigkeit übergeben. Nur Gleitkommawerte werden ganzzahligen Register und die Gleitkommaregister enthalten, wenn von der aufgerufenen Instanz den Wert in der Ganzzahlregister erwartet.  
  
```  
func1();  
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7  
   func1(2, 1.0, 7);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)
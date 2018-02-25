---
title: Pointers_to_members | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
dev_langs:
- C++
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4313aaa38d410b8e6f46594cd9ce11269b523073
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="pointerstomembers"></a>pointers_to_members
**C++-spezifisch**  
  
 Gibt an, ob ein Zeiger auf einen Klassenmember vor der zugeordneten Klassendefinition deklariert werden kann und verwendet wird, um die Zeigergröße und den Code zu steuern, die zum Interpretieren des Zeigers erforderlich sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können platzieren eine **Pointers_to_members** Pragma in der Quelldatei als Alternative zur Verwendung der [/vmx](../build/reference/vmb-vmg-representation-method.md) Compileroptionen oder die [vererbungsschlüsselwörter](../cpp/inheritance-keywords.md).  
  
 Die *Zeigerdeklaration* Argument gibt an, ob Sie einen Zeiger auf ein Element vor oder nach der zugeordneten Funktionsdefinition deklariert haben. Die *Zeigerdeklaration* -Argument ist eines der folgenden zwei Symbole:  
  
|Argument|Kommentare|  
|--------------|--------------|  
|**full_generality**|Generiert sicheren, manchmal nicht optimalen Code. Verwenden Sie **Full_generality** Wenn beliebige Zeiger auf ein Member vor der zugeordneten Klassendefinition deklariert wird. Dieses Argument verwendet immer die zeigerdarstellung, die gemäß der *Most-General-Representation* Argument. Entspricht "/vmg".|  
|**best_case**|Generiert sicheren, optimalen Code unter Verwendung von Best-Case-Darstellung für alle Zeiger auf Member. Erfordert die Definierung der Klasse vor dem Deklarieren eines Zeigers auf einen Member der Klasse. Die Standardeinstellung ist **Best_case**.|  
  
 Die *Most-General-Representation* -Argument gibt die kleinste zeigerdarstellung an, die der Compiler sicher verwenden kann, um beliebige Zeiger auf einen Member einer Klasse in einer Übersetzungseinheit zu referenzieren. Das Argument kann eines der folgenden sein:  
  
|Argument|Kommentare|  
|--------------|--------------|  
|**single_inheritance**|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit einfacher Vererbung. Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, entweder mehrfach oder virtuell ist.|  
|**multiple_inheritance**|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit Mehrfachvererbung. Löst einen Fehler aus, wenn das Vererbungsmodell einer Klassendefinition, für die ein Zeiger auf ein Member deklariert wird, virtuell ist.|  
|**virtual_inheritance**|Die allgemeinste Darstellung ist ein Zeiger auf eine Memberfunktion mit virtueller Vererbung. Löst nie einen Fehler aus. Dies ist das Standardargument beim **#pragma pointers_to_members(full_generality)** verwendet wird.|  
  
> [!CAUTION]
>  Verwenden Sie das `pointers_to_members`-Pragma am besten nur in der Quellcodedatei, für die es gelten soll, und nur nach allen `#include`-Direktiven. Diese Vorgehensweise verringert das Risiko, dass sich das Pragma auf andere Dateien auswirkt, und dass Sie versehentlich mehrere Definitionen für dieselbe Variable oder Funktion oder denselben Klassennamen angeben.  
  
## <a name="example"></a>Beispiel  
  
```  
//   Specify single-inheritance only  
#pragma pointers_to_members( full_generality, single_inheritance )  
```  
  
## <a name="end-c-specific"></a>Ende C++-spezifisch  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
---
title: Optimieren der | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae1988292b1f6dfa35f4cb77d145641528ed827f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="optimize"></a>optimize
Gibt die Optimierungen an, die für jede einzelne Funktion durchgeführt werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **optimieren** Pragma muss außerhalb der Funktion angezeigt werden und wird wirksam, die erste Funktion definiert, nachdem das Pragma angezeigt wird. Die **auf** und **deaktiviert** -Argumenten werden Optionen, die im angegebenen aktiviert die *Optimierungsliste* ein- oder ausschalten.  
  
 Die *Optimierungsliste* kann 0 (null) oder mehrere Parameter in der folgenden Tabelle gezeigt.  
  
### <a name="parameters-of-the-optimize-pragma"></a>Parameter des optimize-Pragmas  
  
|Parameter|Typ der Optimierung|  
|--------------------|--------------------------|  
|**g**|Aktivieren globale Optimierungen.|  
|**s** oder **t**|Geben kurze oder schnelle Sequenzen von Computercode an.|  
|**y**|Generieren Framezeiger im Programmstapel.|  
  
 Hierbei handelt es sich um dieselben Buchstaben verwendet werden, mit der [/o](../build/reference/o-options-optimize-code.md) Compileroptionen. Beispielsweise ist Folgendes Pragma entspricht der **/OS** Compileroption:  
  
```  
#pragma optimize( "ts", on )  
```  
  
 Mithilfe der **optimieren** Pragma mit einer leeren Zeichenfolge (**""**) ist eine besondere Form der Direktive:  
  
 Bei Verwendung der **deaktiviert** Parameter, er wird in der Tabelle weiter oben in diesem Thema aufgeführt sind, deaktiviert Optimierungen.  
  
 Bei Verwendung der **auf** Parameter, die Optimierungen auf zurückgesetzt, die Sie angegeben haben, mit der [/o](../build/reference/o-options-optimize-code.md) -Compileroption.  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
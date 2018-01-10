---
title: Globale Funktionen des Compilers COM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be73622037c1c058edffa681ccd79322b8252633
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-com-global-functions"></a>Globale COM-Funktionen des Compilers
**Microsoft-spezifisch**  
  
 Die folgenden Routinen sind verfügbar:  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[_com_raise_error](../cpp/com-raise-error.md)|Löst ein [_com_error](../cpp/com-error-class.md) in Reaktion auf einen Fehler.|  
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|Ersetzt die Standardfunktion für die COM-Fehlerbehandlung.|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Konvertiert eine `BSTR` -Wert in einen **Char \*** .|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Konvertiert eine **Char \***  -Wert in einen `BSTR`.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Compiler-COM-Unterstützungsklassen](../cpp/compiler-com-support-classes.md)   
 [COM-Unterstützung des Compilers](../cpp/compiler-com-support.md)
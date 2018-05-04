---
title: Globale Funktionen des Compilers COM | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4116d82ef38d7aaab29fe682e0881ac2e2ff5903
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
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
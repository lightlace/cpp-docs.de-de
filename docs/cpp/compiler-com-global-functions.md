---
title: Globale Compiler-COM-Funktionen | Microsoft-Dokumentation
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
ms.openlocfilehash: aa138b045fcb5851a65b68d898b99a8cab269f6e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402532"
---
# <a name="compiler-com-global-functions"></a>Globale COM-Funktionen des Compilers
**Microsoft-spezifisch**  
  
 Die folgenden Routinen sind verfügbar:  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|[_com_raise_error](../cpp/com-raise-error.md)|Löst eine [_com_error](../cpp/com-error-class.md) in Reaktion auf einen Fehler.|  
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|Ersetzt die Standardfunktion für die COM-Fehlerbehandlung.|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Konvertiert eine `BSTR` -Werts in einen `char *`.|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Konvertiert eine `char *` -Werts in einen `BSTR`.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)   
 [COM-Unterstützung des Compilers](../cpp/compiler-com-support.md)
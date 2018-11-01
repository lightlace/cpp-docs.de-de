---
title: Globale COM-Funktionen des Compilers
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
ms.openlocfilehash: ac74270cd020aa66ccc14ff314a00b388a038086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504420"
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

[Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)<br/>
[COM-Unterstützung des Compilers](../cpp/compiler-com-support.md)
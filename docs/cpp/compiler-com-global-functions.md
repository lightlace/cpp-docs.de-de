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
ms.openlocfilehash: cb769cf1419f7a0142a5eeae348ca432f78fb92a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034136"
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
---
title: _com_error-Klasse
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 8ed1521cbf768e5b473281e5f9b7c6597cdc4692
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519554"
---
# <a name="comerror-class"></a>_com_error-Klasse

**Microsoft-spezifisch**

Ein **_com_error** Objekt stellt eine Ausnahmebedingung, die von den Fehlerbehandlungs-Wrapperfunktionen in den Headerdateien, die aus der Typbibliothek generiert oder von einem der COM-Unterstützungsklassen erkannt. Die **_com_error** -Klasse kapselt die HRESULT-Fehlercode und alle zugehörigen `IErrorInfo Interface` Objekt.

### <a name="construction"></a>Konstruktion

|||
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|Erstellt eine **_com_error** Objekt.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](../cpp/com-error-operator-equal.md)|Weist ein vorhandenes **_com_error** zu einem anderen Objekt.|

### <a name="extractor-functions"></a>Funktionen des Extrahierungsprogramms

|||
|-|-|
|[Fehler](../cpp/com-error-error.md)|Ruft den HRESULT-Wert an den Konstruktor übergeben.|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Ruft das `IErrorInfo`-Objekt ab, das an den Konstruktor übergeben wurde.|
|[WCode](../cpp/com-error-wcode.md)|Ruft ab, der 16-Bit-Fehlercode in der gekapselten HRESULT zugeordnet.|

### <a name="ierrorinfo-functions"></a>IErrorInfo-Funktionen

|||
|-|-|
|[Beschreibung](../cpp/com-error-description.md)|Ruft die `IErrorInfo::GetDescription`-Funktion auf.|
|[HelpContext](../cpp/com-error-helpcontext.md)|Ruft die `IErrorInfo::GetHelpContext`-Funktion auf.|
|[HelpFile](../cpp/com-error-helpfile.md)|Ruft die `IErrorInfo::GetHelpFile`-Funktion auf.|
|[Quelle](../cpp/com-error-source.md)|Ruft die `IErrorInfo::GetSource`-Funktion auf.|
|[GUID](../cpp/com-error-guid.md)|Ruft die `IErrorInfo::GetGUID`-Funktion auf.|

### <a name="format-message-extractor"></a>FormatMessage-Extractor

|||
|-|-|
|[ErrorMessage](../cpp/com-error-errormessage.md)|Ruft die Zeichenfolgennachricht ab, für die gespeicherte HRESULT in die **_com_error** Objekt.|

### <a name="exepinfowcode-to-hresult-mappers"></a>ExepInfo.wCode für HRESULT-Zuordnungen

|||
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Ordnet 32-Bit-HRESULT 16-Bit- `wCode`.|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Ordnet die 16-Bit- `wCode` in 32-Bit-HRESULT.|

**Ende Microsoft-spezifisch**

## <a name="requirements"></a>Anforderungen

**Header:** \<comdef.h>

`Lib:` comsuppw.lib oder comsuppwd.lib (finden Sie unter [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Informationen)

## <a name="see-also"></a>Siehe auch

[Compilerklassen für COM-Unterstützung](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo-Schnittstelle](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo)
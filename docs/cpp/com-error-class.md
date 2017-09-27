---
title: _com_error-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 670be1988adb3ef5afa9113b9988ceafb249801f
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comerror-class"></a>_com_error-Klasse
**Microsoft-spezifisch**  
  
 Ein `_com_error`-Objekt stellt eine Ausnahmebedingung dar, die von den Fehlerbehandlungs-Wrapperfunktionen in den Headerdateien erkannt wird, die von der Typbibliothek oder einer der COM-Unterstützungsklassen generiert werden. Die `_com_error`-Klasse kapselt den `HRESULT`-Fehlercode und jedes zugeordnete `IErrorInfo Interface`-Objekt.  
  
### <a name="construction"></a>Konstruktion  
  
|||  
|-|-|  
|[_com_error](../cpp/com-error-com-error.md)|Erstellt ein `_com_error`-Objekt.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator =](../cpp/com-error-operator-equal.md)|Weist ein vorhandenes `_com_error`-Objekt einem anderen zu.|  
  
### <a name="extractor-functions"></a>Funktionen des Extrahierungsprogramms  
  
|||  
|-|-|  
|[Fehler](../cpp/com-error-error.md)|Ruft das an den Konstruktor übergebene `HRESULT` ab.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Ruft das `IErrorInfo`-Objekt ab, das an den Konstruktor übergeben wurde.|  
|[WCode](../cpp/com-error-wcode.md)|Ruft den 16-Bit-Fehlercode ab, der dem gekapselten `HRESULT` zugeordnet ist.|  
  
### <a name="ierrorinfo-functions"></a>IErrorInfo-Funktionen  
  
|||  
|-|-|  
|[Beschreibung](../cpp/com-error-description.md)|Ruft die `IErrorInfo::GetDescription`-Funktion auf.|  
|[HelpContext](../cpp/com-error-helpcontext.md)|Ruft die `IErrorInfo::GetHelpContext`-Funktion auf.|  
|[HelpFile](../cpp/com-error-helpfile.md)|Ruft die `IErrorInfo::GetHelpFile`-Funktion auf.|  
|[Source](../cpp/com-error-source.md)|Ruft die `IErrorInfo::GetSource`-Funktion auf.|  
|[GUID](../cpp/com-error-guid.md)|Ruft die `IErrorInfo::GetGUID`-Funktion auf.|  
  
### <a name="format-message-extractor"></a>FormatMessage-Extractor  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|Ruft die Zeichenfolgenmeldung für das im `_com_error`-Objekt gespeicherte HRESULT ab.|  
  
### <a name="exepinfowcode-to-hresult-mappers"></a>ExepInfo.wCode für HRESULT-Zuordnungen  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Ordnet 32-Bit-`HRESULT` dem 16-Bit-`wCode` zu.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Ordnet die 16-Bit- `wCode` auf 32-Bit- `HRESULT`.|  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** comdef.h  
  
 `Lib:`"comsuppw.lib" oder "comsuppwd.lib" (siehe [/Zc: wchar_t (Wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) für Weitere Informationen)  
  
## <a name="see-also"></a>Siehe auch  
 [Compiler-COM-Unterstützungsklassen](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo-Schnittstelle](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)

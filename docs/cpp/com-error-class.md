---
title: "_com_error-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error-Klasse"
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ein `_com_error`\-Objekt stellt eine Ausnahmebedingung dar, die von den Fehlerbehandlungs\-Wrapperfunktionen in den Headerdateien erkannt wird, die von der Typbibliothek oder einer der COM\-Unterstützungsklassen generiert werden.  Die `_com_error`\-Klasse kapselt den `HRESULT`\-Fehlercode und jedes zugeordnete `IErrorInfo Interface`\-Objekt.  
  
### Konstruktion  
  
|||  
|-|-|  
|[\_com\_error](../cpp/com-error-com-error.md)|Erstellt ein `_com_error`\-Objekt.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator \=](../cpp/com-error-operator-equal.md)|Weist ein vorhandenes `_com_error`\-Objekt einem anderen zu.|  
  
### Funktionen des Extrahierungsprogramms  
  
|||  
|-|-|  
|[Fehler](../cpp/com-error-error.md)|Ruft das an den Konstruktor übergebene `HRESULT` ab.|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|Ruft das `IErrorInfo`\-Objekt ab, das an den Konstruktor übergeben wurde.|  
|[WCode](../cpp/com-error-wcode.md)|Ruft den 16\-Bit\-Fehlercode ab, der dem gekapselten `HRESULT` zugeordnet ist.|  
  
### IErrorInfo\-Funktionen  
  
|||  
|-|-|  
|[Beschreibung](../cpp/com-error-description.md)|Ruft die `IErrorInfo::GetDescription`\-Funktion auf.|  
|[HelpContext](../cpp/com-error-helpcontext.md)|Ruft die `IErrorInfo::GetHelpContext`\-Funktion auf.|  
|[HelpFile](../cpp/com-error-helpfile.md)|Ruft die `IErrorInfo::GetHelpFile`\-Funktion auf.|  
|[Source](../cpp/com-error-source.md)|Ruft die `IErrorInfo::GetSource`\-Funktion auf.|  
|[GUID](../cpp/com-error-guid.md)|Ruft die `IErrorInfo::GetGUID`\-Funktion auf.|  
  
### FormatMessage\-Extractor  
  
|||  
|-|-|  
|[ErrorMessage](../cpp/com-error-errormessage.md)|Ruft die Zeichenfolgenmeldung für das im `_com_error`\-Objekt gespeicherte HRESULT ab.|  
  
### ExepInfo.wCode für HRESULT\-Zuordnungen  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|Ordnet 32\-Bit\-`HRESULT` dem 16\-Bit\-`wCode` zu.|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|Ordnet 16\-Bit\-`wCode` dem 32\-Bit\-`HRESULT` zu.|  
  
## Ende Microsoft\-spezifisch  
  
## Anforderungen  
 `Header:` comdef.h  
  
 `Lib:` comsuppw.lib oder comsuppwd.lib \(Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).\)  
  
## Siehe auch  
 [Compilerklassen für COM\-Unterstützung](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo Interface](assetId:///4dda6909-2d9a-4727-ae0c-b5f90dcfa447)
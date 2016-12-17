---
title: "_com_raise_error"
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
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_raise_error-Funktion"
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# _com_raise_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Löst einen [\_com\_error](../cpp/com-error-class.md) als Reaktion auf einen Fehler aus.  
  
## Syntax  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### Parameter  
 `hr`  
 `HRESULT`\-Informationen.  
  
 `perrinfo`  
 **IErrorInfo**\-Objekt.  
  
## Hinweise  
 `_com_raise_error`, das in comdef.h definiert ist, kann durch eine vom Benutzer erstellte Version desselben Namens und Prototyps ersetzt werden.  Dies kann ausgeführt werden, wenn Sie `#import` verwenden möchten, jedoch nicht die C\+\+\-Ausnahmebehandlung.  In diesem Fall könnte eine Benutzerversion von **\_com\_raise\_error** entscheiden, einen `longjmp` auszuführen oder ein Meldungsfeld anzuzeigen und anzuhalten.  Die Benutzerversion sollte nicht zurückkehren. Denn die COM\-Unterstützung des Compiler\-Codes erwartet keine Rückkehr.  
  
 Sie können auch [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md) verwenden, um die Standardfehlerbehandlungsfunktion zu ersetzen.  
  
 Standardmäßig wird `_com_raise_error` wie folgt definiert:  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
## END Microsoft\-spezifisch  
  
## Anforderungen  
 **Header:** comdef.h  
  
 **Lib:** wenn die Compileroption "wchar\_t ist der systemeigene Typ" aktiviert ist, verwenden Sie "comsuppw.lib" oder "comsuppwd.lib".  Wenn "wchar\_t ist der systemeigene Typ" deaktiviert ist, verwenden Sie "comsupp.lib".  Weitere Informationen finden Sie unter [\/Zc:wchar\_t \(wchar\_t ist der systemeigene Typ\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## Siehe auch  
 [Globale Funktionen des Compiler\-COM](../cpp/compiler-com-global-functions.md)   
 [\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)
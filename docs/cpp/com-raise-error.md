---
title: _com_raise_error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_raise_error
dev_langs: C++
helpviewer_keywords: _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cfb51d4188917ebcdbad2fead13a9792875d2f11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft-spezifisch**  
  
 Löst ein [_com_error](../cpp/com-error-class.md) in Reaktion auf einen Fehler.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hr`  
 `HRESULT`-Informationen.  
  
 `perrinfo`  
 **IErrorInfo** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 `_com_raise_error`, das in comdef.h definiert ist, kann durch eine vom Benutzer erstellte Version desselben Namens und Prototyps ersetzt werden. Dies kann ausgeführt werden, wenn Sie `#import` verwenden möchten, jedoch nicht die C++-Ausnahmebehandlung. In diesem Fall kann eine Version **_com_raise_error** führen Sie ggf. eine `longjmp` oder Anzeigen eines Meldungsfelds und anzuhalten. Die Benutzerversion sollte nicht zurückkehren. Denn die COM-Unterstützung des Compiler-Codes erwartet keine Rückkehr.  
  
 Sie können auch [_set_com_error_handler](../cpp/set-com-error-handler.md) ersetzt die Standardfunktion für die Fehlerbehandlung.  
  
 Standardmäßig wird `_com_raise_error` wie folgt definiert:  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** comdef.h  
  
 **LIB:** Wenn die **Wchar_t ist der systemeigene Typ** Compileroption ist, verwenden Sie "comsuppw.lib" oder "comsuppwd.lib". Wenn **Wchar_t ist der systemeigene Typ** deaktiviert ist, verwenden "comsupp.lib". Weitere Informationen finden Sie unter[/Zc:wchar_t (wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Compiler-COM-Funktionen](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)
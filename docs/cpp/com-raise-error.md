---
title: _com_raise_error | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54cb2183bccc45446cd68b8d5d6d2753f571009b
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408088"
---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft-spezifisch**  
  
 Löst eine [_com_error](../cpp/com-error-class.md) in Reaktion auf einen Fehler.  
  
## <a name="syntax"></a>Syntax  
  
```  
void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *HR*  
 HRESULT-Informationen.  
  
 *perrinfo*  
 `IErrorInfo`-Objekt  
  
## <a name="remarks"></a>Hinweise  
 **_com_raise_error**, definiert in \<comdef.h >, kann durch eine vom Benutzer erstellte Version den gleichen Namen und der Prototyp ersetzt werden. Dies kann ausgeführt werden, wenn Sie `#import` verwenden möchten, jedoch nicht die C++-Ausnahmebehandlung. In diesem Fall kann eine Version **_com_raise_error** könnten Sie eine `longjmp` oder ein Meldungsfeld anzuzeigen und anzuhalten. Die Benutzerversion sollte nicht zurückkehren. Denn die COM-Unterstützung des Compiler-Codes erwartet keine Rückkehr.  
  
 Sie können auch [_set_com_error_handler](../cpp/set-com-error-handler.md) ersetzt die Standardfunktion für die Fehlerbehandlung.  
  
 In der Standardeinstellung **_com_raise_error** ist wie folgt definiert:  
  
```cpp  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<comdef.h>  
  
 **LIB:** Wenn die **Wchar_t ist der systemeigene Typ** Compileroption aktiviert ist, verwenden Sie comsuppw.lib oder comsuppwd.lib. Wenn **Wchar_t ist der systemeigene Typ** deaktiviert ist, sollten Sie comsupp.lib verwenden. Weitere Informationen finden Sie unter[/Zc:wchar_t (wchar_t ist der systemeigene Typ)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globale Compiler-COM-Funktionen](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)
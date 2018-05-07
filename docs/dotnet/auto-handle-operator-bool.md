---
title: Bool auto_handle::Operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_handle.operator bool
- msclr.auto_handle.operator bool
- operator bool
- msclr::auto_handle::operator bool
- auto_handle::operator bool
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::operator bool
ms.assetid: 2e535e99-cf87-4008-b588-02c587d77453
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 562aefc72a8ce2738a78527dcdc6a73f606a7627
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="autohandleoperator-bool"></a>auto_handle::operator bool
Operator für die Verwendung von `auto_handle` in einem bedingten Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator bool();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn das umschlossene Objekt gültig ist. `false` andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Operator konvertiert tatsächlich in `_detail_class::_safe_bool` ist sicherer als `bool` , da es zu einem ganzzahligen Typ konvertiert werden kann.  
  
## <a name="example"></a>Beispiel  
  
```  
// msl_auto_handle_operator_bool.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1;  
   auto_handle<String> s2 = "hi";  
   if ( s1 ) Console::WriteLine( "s1 is valid" );  
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );  
   if ( s2 ) Console::WriteLine( "s2 is valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );  
   s2.reset();  
   if ( s2 ) Console::WriteLine( "s2 is now valid" );  
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );  
}  
```  
  
```Output  
s1 is invalid  
s2 is valid  
s2 is now invalid  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\auto_handle.h >  
  
 **Namespace** Msclr  
  
## <a name="see-also"></a>Siehe auch  
 [Auto_handle-Member](../dotnet/auto-handle-members.md)   
 [auto_handle::operator!](../dotnet/auto-handle-operator-logical-not.md)
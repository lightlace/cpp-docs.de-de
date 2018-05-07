---
title: Bool auto_gcroot::Operator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_gcroot.operator bool
- auto_gcroot::operator bool
- msclr.auto_gcroot.operator bool
- msclr::auto_gcroot::operator bool
- operator bool
dev_langs:
- C++
helpviewer_keywords:
- bool operator
ms.assetid: 87d38498-4221-4de8-8d02-c2dd2e6274ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8dbb38ecfa7f1a60af44a59ccd1953b6d6e787fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="autogcrootoperator-bool"></a>auto_gcroot::operator bool
Operator für die Verwendung von `auto_gcroot` in einem bedingten Ausdruck.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator bool() const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn das umschlossene Objekt gültig ist. `false` andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Operator konvertiert tatsächlich in `_detail_class::_safe_bool` ist sicherer als `bool` , da es zu einem ganzzahligen Typ konvertiert werden kann.  
  
## <a name="example"></a>Beispiel  
  
```  
// msl_auto_gcroot_operator_bool.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_gcroot<String^> s;  
   if ( s ) Console::WriteLine( "s is valid" );  
   if ( !s ) Console::WriteLine( "s is invalid" );  
   s = "something";  
   if ( s ) Console::WriteLine( "now s is valid" );  
   if ( !s ) Console::WriteLine( "now s is invalid" );  
   s.reset();  
   if ( s ) Console::WriteLine( "now s is valid" );  
   if ( !s ) Console::WriteLine( "now s is invalid" );  
}  
```  
  
```Output  
s is invalid  
now s is valid  
now s is invalid  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Headerdatei** \<msclr\auto_gcroot.h >  
  
 **Namespace** Msclr  
  
## <a name="see-also"></a>Siehe auch  
 [Auto_gcroot-Elemente](../dotnet/auto-gcroot-members.md)   
 [auto_gcroot::operator!](../dotnet/auto-gcroot-operator-logical-not.md)
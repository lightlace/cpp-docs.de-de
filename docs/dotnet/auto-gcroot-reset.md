---
title: auto_gcroot::Reset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::reset
- auto_gcroot::reset
- msclr.auto_gcroot.reset
- auto_gcroot.reset
dev_langs:
- C++
helpviewer_keywords:
- reset method
ms.assetid: dd58467f-3885-4a15-99fb-ed6dd5d19622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9202c9c08b7291a2d202eacef79160c587d84563
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446089"
---
# <a name="autogcrootreset"></a>auto_gcroot::reset

Zerstören Sie das aktuelle Objekt für die im Besitz des Benutzers und optional ein neues Objekt besitzt.

## <a name="syntax"></a>Syntax

```
void reset(
   _element_type _new_ptr = nullptr
);
```

#### <a name="parameters"></a>Parameter

*_new_ptr*<br/>
(Optional) Das neue Objekt.

## <a name="example"></a>Beispiel

```
// msl_auto_gcroot_reset.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {
      Console::WriteLine( "ClassA constructor: " + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "ClassA destructor: " + m_s );
   }

   void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

int main()
{
   auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );
   agc1->PrintHello();

   ClassA^ ha = gcnew ClassA( "second" );
   agc1.reset( ha ); // release first object, reference second
   agc1->PrintHello();

   agc1.reset(); // release second object, set to nullptr

   Console::WriteLine( "done" );
}
```

```Output
ClassA constructor: first
Hello from first A!
ClassA constructor: second
ClassA destructor: first
Hello from second A!
ClassA destructor: second
done
```

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\auto_gcroot.h >

**Namespace** Msclr

## <a name="see-also"></a>Siehe auch

[auto_gcroot-Members](../dotnet/auto-gcroot-members.md)<br/>
[auto_gcroot::release](../dotnet/auto-gcroot-release.md)<br/>
[auto_gcroot::attach](../dotnet/auto-gcroot-attach.md)
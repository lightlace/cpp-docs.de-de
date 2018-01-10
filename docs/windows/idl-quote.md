---
title: Idl_quote | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.idl_quote
dev_langs: C++
helpviewer_keywords: idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 288d90bf2e32024792eaf5ec44825a9ac992bd71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idlquote"></a>idl_quote
Ermöglicht es Ihnen IDL-Konstrukte zu verwenden, die nicht in der aktuellen Version von Visual C++ unterstützt werden, und lassen sie die pass-through an der generierten IDL-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### <a name="parameters"></a>Parameter  
 *Text*  
 Der Attributname, das Visual C++-Compiler, pass-through an der generierten IDL-Datei ohne einen Compilerfehler zurückgegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die **Idl_quote** C++-Attribut dient als eigenständiges Attribut (mit einem Semikolon nach der schließenden Klammer einfügen), klicken Sie dann *Text* befindet sich in der zusammengeführten IDL-Datei ist. Wenn **Idl_quote** wird verwendet, auf ein Symbol *Text* innerhalb des Attributblocks für das Symbol befindet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie ein nicht unterstütztes Attribut angeben können (mit **in**, dies wird jedoch unterstützt) sowie zum Definieren und verwenden ein nicht definierter IDL-Konstrukt:  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 Dieser Code bewirkt, dass MYFLOT und MYDUB und die *Text* Eintrag in der generierten IDL-Datei abgelegt werden soll. Die *Namen* Parameter erzwingt *Text* vor allem abgelegt werden soll, die verweist *Namen* in der generierten IDL-Datei. Die *Abhängigkeiten* Parameter erzwingt, dass die Abhängigkeit Listendefinitionen vor platziert werden *Text* in der generierten IDL-Datei.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Eigenständige Attribute](../windows/stand-alone-attributes.md)   

---
title: Platform::Metadata::RuntimeClassName | Microsoft Docs
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
caps.latest.revision: "2"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 301e012c1d421348ea252019d892b2e526d6aefc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName
Stellt bei Anwendung auf eine Klassendefinition sicher, dass eine private Klasse einen gültigen Namen aus der GetRuntimeClassName-Funktion zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[Platform::Metadata::RuntimeClassName] name  
```  
  
#### <a name="parameters"></a>Parameter  
 Name  
  
 Der Name eines vorhandenen öffentlichen Typs, der in der Windows-Runtime sichtbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Attribut bei privaten Verweisklassen, um einen allgemeinen Laufzeittypnamen anzugeben, oder verwenden Sie es, wenn der vorhandene Name nicht den Anforderungen entspricht. Geben Sie als Namen eine öffentliche Schnittstelle ein, die die Klasse implementiert.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie das Attribut verwenden. In diesem Beispiel lautet der Laufzeittypname von HellowWorldImpl Test::Native::MyComponent::IHelloWorld  
  
```  
  
namespace Test  
{  
    namespace Native  
    {  
        namespace MyComponent  
        {  
            public interface class IHelloWorld  
            {  
                Platform::String^ SayHello();  
            };  
  
            private ref class HelloWorldImpl sealed :[Platform::Metadata::RuntimeClassName] IHelloWorld  
            {  
            public:  
                HelloWorldImpl();  
                virtual Platform::String^ SayHello();  
            };  
  
            Platform::String^ HelloWorldImpl::SayHello()  
            {  
                return L"Hello World!";  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Platform::Metadata-Namespace](../cppcx/platform-metadata-namespace.md)
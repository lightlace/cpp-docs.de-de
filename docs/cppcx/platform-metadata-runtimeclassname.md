---
title: Platform::Metadata::RuntimeClassName | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 297a5089af7db43d837934e864e0925cd7b34a3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
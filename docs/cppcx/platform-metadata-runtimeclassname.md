---
title: Platform::Metadata::RuntimeClassName
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::RuntimeClassName
helpviewer_keywords:
- RuntimeClassName
- Platform::Metadata::RuntimeClassName
ms.assetid: fdef8f85-ab94-4edd-ba50-ee0da9358ff6
ms.openlocfilehash: d3de753c3a8897058333e02ce4294a0780d5b818
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387577"
---
# <a name="platformmetadataruntimeclassname"></a>Platform::Metadata::RuntimeClassName

Stellt bei Anwendung auf eine Klassendefinition sicher, dass eine private Klasse einen gültigen Namen aus der GetRuntimeClassName-Funktion zurückgibt.

## <a name="syntax"></a>Syntax

```cpp
[Platform::Metadata::RuntimeClassName] name
```

#### <a name="parameters"></a>Parameter

*name*<br/>
Der Name eines vorhandenen öffentlichen Typs, der in der Windows-Runtime sichtbar ist.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Attribut bei privaten Verweisklassen, um einen allgemeinen Laufzeittypnamen anzugeben, oder verwenden Sie es, wenn der vorhandene Name nicht den Anforderungen entspricht. Geben Sie als Namen eine öffentliche Schnittstelle ein, die die Klasse implementiert.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie das Attribut verwenden. In diesem Beispiel lautet der Laufzeittypname von HellowWorldImpl Test::Native::MyComponent::IHelloWorld

```cpp
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

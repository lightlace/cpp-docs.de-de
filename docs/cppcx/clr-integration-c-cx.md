---
title: CLR-Integration (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: 44ef35d1a62706cae37285c06547a8b9b7deb35c
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740295"
---
# <a name="clr-integration-ccx"></a>CLR-Integration (C++/CX)

Einige Windows-Runtime Typen erhalten eine spezielle Behandlung C++in/CX und die Sprachen, die auf dem Common Language Runtime (CLR) basieren. Dieser Artikel behandelt, wie verschiedene Typen in einer Sprache einer anderen Sprache zugeordnet werden. Beispielsweise ordnet die CLR „Windows.Foundation.IVector“ zu „System.Collections.IList“, „Windows.Foundation.IMap“ zu „System.Collections.IDictionary“ zu usw. Ebenso ordnet C++/CX speziell Typen wie Platform::D Elegate und Platform:: String zu.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Zuordnung des Windows-Runtime zu C++/CX

Wenn C++/CX eine Windows-Metadatendatei (. winmd) liest, ordnet der Compiler allgemeine Windows-Runtime Namespaces und Typen C++automatisch/CX-Namespaces und-Typen zu. Der numerische Windows-Runtime Typ `UInt32` wird z. b. automatisch zugeordnet. `default::uint32`

C++/CX ordnet mehrere andere Windows-Runtime Typen dem **Platform** -Namespace zu. Beispielsweise wird das hstring-Handle von **Windows:: Foundation** , das eine schreibgeschützte Unicode-Text Zeichenfolge darstellt, C++der `Platform::String` /CX-Klasse zugeordnet. Wenn ein Windows-Runtime Vorgang einen Fehler HRESULT zurückgibt, wird er einem C++/CX `Platform::Exception`zugeordnet.

Der C++/CX ordnet auch bestimmte Typen in Windows-Runtime Namespaces zu, um die Funktionalität des Typs zu verbessern. Für diese Typen stellt C++/CX Hilfskonstruktoren und Methoden bereit, die für C++ spezifisch sind und in der Datei "Standard. winmd" des Typs nicht verfügbar sind.

Die folgende Liste enthält Wertstrukturen, die neue Konstruktoren und Hilfsmethoden unterstützen. Wenn Sie bisher Code erstellt haben, der mit Strukturinitialisierungslisten arbeitet, stellen Sie ihn auf die neu hinzugefügten Konstruktoren um.

**Windows::Foundation**

- Punkt

- Rect

- Größe

**Windows::UI**

- Farbe

**Windows::UI::Xaml**

- CornerRadius

- Dauer

- GridLength

- Stärke

**Windows::UI::Xaml::Interop**

- TypeName

**Windows::UI::Xaml::Media**

- Matrix

**Windows::UI::Xaml::Media::Animation**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>Mapping der CLR zu C++/CX

Wenn Microsoft C++ oder C# Compiler eine winmd-Datei lesen, ordnen Sie bestimmte Typen in der Metadatendatei automatisch den entsprechenden C++/CX-oder CLR-Typen zu. In der CLR wird z. b. die IVector\<t->-Schnittstelle IList\<t > zugeordnet. In C++/CX ist die IVector\<T >-Schnittstelle jedoch keinem anderen Typ zugeordnet.

Die IReference\<t-> im Windows-Runtime wird in .net\<zu Nullable t > zugeordnet.

## <a name="see-also"></a>Siehe auch

[Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)

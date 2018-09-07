---
title: CLR-Integration (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95dd817e7081eea6371e9dab9d95aec06d22971c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110765"
---
# <a name="clr-integration-ccx"></a>CLR-Integration (C++/CX)

Einige Windows-Runtime-Typen erhalten Sie spezielle Behandlung in C++ / CX und die Sprachen an, die auf die common Language Runtime (CLR) basieren. Dieser Artikel behandelt, wie verschiedene Typen in einer Sprache einer anderen Sprache zugeordnet werden. Beispielsweise ordnet die CLR „Windows.Foundation.IVector“ zu „System.Collections.IList“, „Windows.Foundation.IMap“ zu „System.Collections.IDictionary“ zu usw. Auf ähnliche Weise C + c++ / CX ordnet Typen wie z. B. Delegate "und" Platform:: String.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Zuordnen von der Windows-Runtime für C++ / CX

Wenn C++ / CX liest eine Windows-Metadatendatei (.winmd), ordnet der Compiler automatisch gemeinsame Windows-Runtime-Namespaces und Typen für C++ / CX-Namespaces und Typen. Z. B. den numerischen Typ Windows-Runtime `UInt32` automatisch zugeordnet ist `default::uint32`.

C++ / CX ordnet mehrere andere Windows-Runtime-Typen an die **Plattform** Namespace. Z. B. die **Windows:: Foundation** HSTRING-Handle, das eine schreibgeschützte Unicode-Textzeichenfolge darstellt, zugeordnet ist C++ / CX `Platform::String` Klasse. Ein Windows-Runtime-Vorgang einen Fehler HRESULT zurückgibt, zugeordnet, um C++ / CX `Platform::Exception`.

C++ / CX ordnet darüber hinaus bestimmte Typen in Windows-Runtime-Namespaces, um die Funktionalität des Typs zu verbessern. Für diese Typen stellt C++ / CX stellt hilfskonstruktoren und Methoden, die für C++ spezifisch sind, und sind in den Typ der standardmäßigen winmd-Datei nicht verfügbar.

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

## <a name="mapping-the-clr-to-ccx"></a>Zuordnen der CLR für C++ / CX

Wenn die Visual C++ oder c#-Compiler eine winmd-Datei lesen, ordnen sie automatisch bestimmte Typen in der Metadatendatei für entsprechende C++ / CX- oder CLR-Datentypen. Z. B. in der CLR, die IVector\<T >-Schnittstelle IList zugeordnet ist\<T >. Aber in C++ / CX, die IVector\<T >-Schnittstelle ist nicht in einen anderen Typ zugeordnet.

"IReference"\<T > in der Windows-Runtime ordnet Nullable\<T > in .NET.

## <a name="see-also"></a>Siehe auch

[Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)
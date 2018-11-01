---
title: Typweiterleitung (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- type forwarding, C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7fe70de2503134bf76f5e1c7099773737cc153f8
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328336"
---
# <a name="type-forwarding-ccli"></a>Typweiterleitung (C++/CLI)

*Typweiterleitung* können Sie einen Typ aus einer Assembly (Assembly A) in einer anderen Assembly (Assembly B), zu verschieben, so, dass es nicht erforderlich ist, Clients, die Assembly a zu verwenden, neu kompilieren

## <a name="windows-runtime"></a>Windows-Runtime

Dieses Feature wird in der Windows-Runtime nicht unterstützt.

## <a name="common-language-runtime"></a>Common Language Runtime

Im folgenden Codebeispiel wird veranschaulicht, wie die typweiterleitung wird.

### <a name="syntax"></a>Syntax

```cpp
#using "new.dll"
[assembly:TypeForwardedTo(type::typeid)];
```

### <a name="parameters"></a>Parameter

*new*<br/>
Die Assembly, in der Sie die Typdefinition verschieben.

*Typ*<br/>
Der Typ, dessen Definition, die Sie in eine andere Assembly verschieben.

### <a name="remarks"></a>Hinweise

Wenn eine Komponente (Assembly) enthalten ist und von Clientanwendungen verwendet wird, können Sie die typweiterleitung zum Verschieben eines Typs von der Komponente (Assembly) in einer anderen Assembly ausgeliefert, die aktualisierte Komponente (und alle zusätzlichen Assemblys, die erforderlich sind) und dem Client Anwendungen sind weiterhin funktionsfähig, ohne Sie erneut kompiliert wird.

Typweiterleitung funktioniert nur für Komponenten, die von einer vorhandenen Anwendung verwiesen wird. Wenn Sie eine Anwendung neu erstellen, muss die entsprechenden Assemblyverweise für alle Typen, die in der Anwendung verwendeten vorhanden sein.

Wenn einen Typ (Typ A) aus einer Assembly weiterleiten zu können, müssen Sie Hinzufügen der `TypeForwardedTo` -Attribut für diesen Typ als auch ein Assemblyverweis. Die Assembly, die Sie verweisen, muss es sich um einen der folgenden enthalten:

- Die Definition für den Typ a

- Ein `TypeForwardedTo` Attribut geben Sie einen als auch ein Assemblyverweis.

Beispiele für Typen, die weitergeleitet werden können, sind:

- Verweisklassen

- Wertklassen

- Enumerationen

- Schnittstellen

Sie können die folgenden Typen nicht weiterleiten:

- Generische Typen

- Systemeigene Typen

- Geschachtelte Typen (Wenn Sie einen geschachtelten Typ weiterleiten möchten, Sie sollten weiterleiten den einschließenden Typ)

Sie können einen Typ in einer Assembly, die in alle Sprachen für die common Language Runtime erstellt weiterleiten.

Wenn eine Quellcodedatei, die verwendet wird, zum Erstellen einer Assembly A.dll eine Typdefinition enthält also (`ref class MyClass`), und Sie diesen Typ verschieben möchten Definition Assembly B.dll, Sie würden:

1. Verschieben der `MyClass` Typdefinition auf eine Quellcodedatei, die zum Erstellen von B.dll verwendet.

2. Erstellen Sie die Assembly B.dll

3. Löschen der `MyClass` Typdefinition aus dem Quellcode verwendet, um A.dll erstellen, und Ersetzen Sie ihn durch Folgendes:

    ```cpp
    #using "B.dll"
    [assembly:TypeForwardedTo(MyClass::typeid)];
    ```

4. Erstellen Sie die Assembly A.dll.

5. Verwenden Sie A.dll ohne erneute Kompilierung von Clientanwendungen.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`
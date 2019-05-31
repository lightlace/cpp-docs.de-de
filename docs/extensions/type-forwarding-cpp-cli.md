---
title: Typweiterleitung (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- type forwarding, C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
ms.openlocfilehash: c5148c05e5580942d885b310e35f3b629224a654
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515975"
---
# <a name="type-forwarding-ccli"></a>Typweiterleitung (C++/CLI)

Mit *Typweiterleitung* können Sie einen Typ aus einer Assembly (Assembly A) in eine andere Assembly (Assembly B) verschieben, sodass es nicht erforderlich ist, Clients, die Assembly A verwenden, neu zu kompilieren.

## <a name="windows-runtime"></a>Windows-Runtime

Dieses Feature wird in der Windows-Runtime nicht unterstützt.

## <a name="common-language-runtime"></a>Common Language Runtime

Im folgenden Codebeispiel wird die Verwendung dieses Typs veranschaulicht.

### <a name="syntax"></a>Syntax

```cpp
#using "new.dll"
[assembly:TypeForwardedTo(type::typeid)];
```

### <a name="parameters"></a>Parameter

*new*<br/>
Die Assembly, in die Sie die Typdefinition verschieben.

*Typ*<br/>
Der Typ, dessen Definition Sie in eine andere Assembly verschieben.

### <a name="remarks"></a>Anmerkungen

Wenn eine Komponente (Assembly) geliefert ist und von Clientanwendungen verwendet wird, können Sie mit der Typweiterleitung einen Typ von der Komponente (Assembly) in eine andere Assembly verschieben, die aktualisierte Komponente (und alle zusätzlichen erforderlichen Assemblys) liefern, und die Clientanwendungen sind weiterhin funktionsfähig, ohne erneut kompiliert zu werden.

Typweiterleitung funktioniert nur für Komponenten, auf die vorhandene Anwendungen verweisen. Wenn Sie eine Anwendung neu erstellen, müssen die entsprechenden Assemblyverweise für alle in der Anwendung verwendeten Typen vorhanden sein.

Beim Weiterleiten eines Typs (Typ A) aus einer Assembly müssen Sie das `TypeForwardedTo`-Attribut für diesen Typ sowie einen Assemblyverweis hinzufügen. Die Assembly, auf die Sie verweisen, muss eine der folgenden Alternativen enthalten:

- Die Definition für Typ A.

- Ein `TypeForwardedTo`-Attribut für Typ A sowie einen Assemblyverweis.

Zu den Beispielen für Typen, die weitergeleitet werden können, zählen:

- Verweisklassen

- Wertklassen

- Enumerationen

- Schnittstellen

Sie können die folgenden Typen nicht weiterleiten:

- Generische Typen

- Native Typen

- Geschachtelte Typen (wenn Sie einen geschachtelten Typ weiterleiten möchten, sollten Sie den einschließenden Typ weiterleiten)

Sie können einen Typ zu einer Assembly weiterleiten, die in einer beliebigen, der Common Language Runtime entsprechenden Sprache erstellt wurde.

Wenn also eine Quellcodedatei, die zum Erstellen der Assembly „A.dll“ verwendet wird, eine Typdefinition enthält (`ref class MyClass`), und Sie diese Typdefinition zu Assembly „B.dll“ verschieben möchten, gehen Sie wie folgt vor:

1. Verschieben Sie die `MyClass`-Typdefinition in eine Quellcodedatei, die zum Erstellen von „B.dll“ verwendet wird.

2. Erstellen Sie Assembly „B.dll“.

3. Löschen Sie die `MyClass`-Typdefinition aus dem zum Erstellen von „A.dll“ verwendeten Quellcode, und ersetzen Sie sie durch Folgendes:

    ```cpp
    #using "B.dll"
    [assembly:TypeForwardedTo(MyClass::typeid)];
    ```

4. Erstellen Sie Assembly „A.dll“.

5. Verwenden Sie „A.dll“ ohne erneute Kompilierung von Clientanwendungen.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`
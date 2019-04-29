---
title: Compilerwarnung (Stufe 1) C4462
ms.date: 10/25/2017
f1_keywords:
- C4462
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
ms.openlocfilehash: bd4d5c1fd7dd8d7419fc901149ceab7e769e7076
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404051"
---
# <a name="compiler-warning-level-1-c4462"></a>Compilerwarnung (Stufe 1) C4462

> Ermitteln der GUID des Typs nicht möglich. Das Programm kann zur Laufzeit fehlschlagen.

Warnung C4462 tritt in einer Windows Runtime-App oder - Komponente auf, wenn ein öffentlicher `TypedEventHandler` als Typparameter einen Verweis auf die übergeordnete Klasse besitzt.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma-Warnung](../../preprocessor/warning.md). Fügen Sie z. B. um C4462 in eine Warnung der Stufe 4 zu machen, diese Zeile auf die Quellcodedatei:

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>Beispiel

In diesem Beispiel wird die Warnung C4462 generiert:

```cpp
namespace N
{
    public ref struct EventArgs sealed {};
    public ref struct R sealed
    {
        R() {}
        event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
    };
}

[Platform::MTAThread]
int main()
{
    auto x = ref new N::R();
}
```

Es gibt zwei Möglichkeiten, den Fehler zu umgehen. Eine Möglichkeit besteht, wie im folgenden Beispiel dargestellt, darin, dem Ereignis internen Zugriff zu gewähren und es somit für den Code in derselben ausführbaren Datei verfügbar zu machen, jedoch nicht für den Code in anderen Windows Runtime-Komponenten.

```cpp
internal:
    event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
```

Wenn das Ereignis öffentlich sein muss, können Sie es mithilfe der anderen Problemumgehung über eine Standardschnittstelle verfügbar machen:

```cpp
ref struct R;
public interface struct IR{ event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;};

public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR
{
    R() {}
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
};
```

Eine GUID vom Typ `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^` wird nur verwendet, wenn eine andere Komponente auf den Typ zugreift. Die erste Problemumgehung funktioniert, da auf sie anschließend nur innerhalb der eigenen Komponente zugegriffen werden kann. Andernfalls muss der Compiler den schlimmsten Fall annehmen und die Warnung ausgeben.

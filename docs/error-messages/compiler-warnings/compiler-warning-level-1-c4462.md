---
title: Compilerwarnung (Stufe 1) C4462 | Microsoft Docs
ms.date: 10/25/2017
ms.technology: cpp-tools
ms.topic: error-reference
f1_keywords: C4462
dev_langs: C++
helpviewer_keywords: C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 95fef51c6b96146842413cd52ab203b747247398
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4462"></a>Compilerwarnung (Stufe 1) C4462

> Ermitteln der GUID des Typs nicht möglich. Das Programm kann zur Laufzeit fehlschlagen.

Warnung C4462 tritt in einer Windows Runtime-App oder - Komponente auf, wenn ein öffentlicher `TypedEventHandler` als Typparameter einen Verweis auf die übergeordnete Klasse besitzt.

Diese Warnung wird automatisch zu einem Fehler heraufgestuft. Wenn Sie dieses Verhalten ändern möchten, verwenden Sie [#pragma Warning](../../preprocessor/warning.md). Fügen Sie z. B. um C4462 in eine Warnung der Stufe 4 zu machen, diese Zeile auf die Quellcodedatei:

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

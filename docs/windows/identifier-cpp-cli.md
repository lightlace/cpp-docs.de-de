---
title: __identifier (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee4aa1686980d2baecd0b261a615818fc5a6c0ee
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082592"
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)

Ermöglicht die Verwendung von C++-Schlüsselwörter als Bezeichner.

## <a name="all-platforms"></a>Alle Plattformen

### <a name="syntax"></a>Syntax

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>Hinweise

Verwenden der **__identifier** Schlüsselwort für Bezeichner entsprechen, die keine Schlüsselwörter sind zulässig, jedoch nicht empfohlen, als eine Frage des Stils.

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

### <a name="examples"></a>Beispiele

**Beispiel**

Im folgenden Beispiel wird eine Klasse namens **Vorlage** in c# erstellt wurde und als eine DLL-Datei verteilt wird. In C++ / CLI-Programm, das verwendet die **Vorlage** -Klasse, die **__identifier** Schlüsselwort verbirgt die Tatsache, **Vorlage** ist ein standard C++-Schlüsselwort.

```cs
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /ZW
#using <identifier_template.dll>
int main() {
   __identifier(template)^ pTemplate = ref new __identifier(template)();
   pTemplate->Run();
}
```

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>Hinweise

Die **__identifier** Schlüsselwort ist gültig, mit der `/clr` -Compileroption.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Im folgenden Beispiel wird eine Klasse namens **Vorlage** in c# erstellt wurde und als eine DLL-Datei verteilt wird. In C++ / CLI-Programm, das verwendet die **Vorlage** -Klasse, die **__identifier** Schlüsselwort verbirgt die Tatsache, **Vorlage** ist ein standard C++-Schlüsselwort.

```cs
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /clr
#using <identifier_template.dll>

int main() {
   __identifier(template) ^pTemplate = gcnew __identifier(template)();
   pTemplate->Run();
}
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)<br/>
[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)
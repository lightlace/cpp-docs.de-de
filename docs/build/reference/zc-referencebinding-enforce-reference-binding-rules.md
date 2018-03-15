---
title: /Zc:referenceBinding (Verweis Bindungsregeln erzwingen) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8e3b10f5b2108a4c0e29d802951015749775a27
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (Verweis Bindungsregeln erzwingen)

Wenn die **/Zc:referenceBinding** angegeben wird, der Compiler lässt sich nicht auf einen nicht konstantes Lvalue-Verweis zum Binden an einen temporären.

## <a name="syntax"></a>Syntax

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>Hinweise

Wenn **/Zc:referenceBinding** angegeben wird, der Compiler 8.5.3 Teil der C ++ 11-standard folgt und lässt keine Ausdrücke, die einen benutzerdefinierten Typ temporäre an ein nicht konstantes Lvalue-Verweis zu binden. Standardmäßig oder wenn **/Zc:referenceBinding-** angegeben wird, der Compiler kann solche Ausdrücke als Microsoft-Erweiterung, aber es wird eine Warnung der Stufe 4 ausgegeben. Für die Codezugriffssicherheit, Portabilität und Übereinstimmung, wir empfehlen die Verwendung **/Zc:referenceBinding**.

Die **/Zc:referenceBinding** Option ist standardmäßig deaktiviert. Die [/ liberalen-](permissive-standards-conformance.md) Compileroption legt implizit diese Option, jedoch können sie mithilfe von außer Kraft gesetzt werden **/Zc:referenceBinding-**.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die Microsoft-Erweiterung, die eine temporäre eines benutzerdefinierten Typs auf einen nicht Konstanten Lvalue-Verweis gebunden werden kann.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:referenceBinding** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>

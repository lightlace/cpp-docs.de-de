---
title: Versiegeln einer virtuellen Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 69ac614d55ade10b94621da2a3eb1c43d25ebaf5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385182"
---
# <a name="sealing-a-virtual-function"></a>Versiegeln einer virtuellen Funktion

Die Syntax für das Versiegeln einer virtuellen Funktion hat Visual c++ von Managed Extensions for C++ geändert.

Die `__sealed` -Schlüsselwort wird in Managed Extensions verwendet, so ändern Sie entweder einen Verweistyp, nachfolgende Ableitung von untersagen (finden Sie unter [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md)), oder ändern eine virtuelle Funktion, verhindern nachfolgende der Methode in einer abgeleiteten Klasse überschreiben. Zum Beispiel:

```
__gc class base { public: virtual void f(); };
__gc class derived : public base {
public:
   __sealed void f();
};
```

In diesem Beispiel `derived::f()` überschreibt die `base::f()` -Instanz basierend auf die genaue Übereinstimmung des Funktionsprototyps. Die `__sealed` -Schlüsselwort Gibt an, dass es sich bei eine nachfolgenden Klasse geerbt von der abgeleiteten Klasse eine Überschreibung der nicht bereitstellen kann `derived::f()`.

In der neuen Syntax `sealed` befindet sich nach der Signatur und nicht zulässiger an einer beliebigen Stelle vor dem tatsächlichen Funktionsprototyp, angezeigt werden, wie zuvor möglich war. Darüber hinaus die Verwendung von `sealed` erfordert eine explizite Verwendung von der `virtual` -Schlüsselworts. D. h. die ordnungsgemäße Übersetzung von `derived`weiter oben, lautet wie folgt:

```
ref class derived: public base {
public:
   virtual void f() override sealed;
};
```

Das Fehlen der `virtual` Schlüsselwort in dieser Instanz führt zu einem Fehler. In der neuen Syntax wird das kontextabhängige Schlüsselwort `abstract` kann verwendet werden, anstelle von der `=0` um eine rein virtuelle Funktion anzugeben. Dies wurde in Managed Extensions nicht unterstützt. Zum Beispiel:

```
__gc class base { public: virtual void f()=0; };
```

kann wie folgt umgearbeitet werden

```
ref class base { public: virtual void f() abstract; };
```

## <a name="see-also"></a>Siehe auch

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[sealed](../windows/sealed-cpp-component-extensions.md)
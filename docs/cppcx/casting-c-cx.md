---
title: Umwandlung von Typen (C + c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 06/19/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66c0e6bc9d987c400c709e74586e6e37ccc0b715
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "36305994"
---
# <a name="casting-ccx"></a>Umwandlung von Typen (C++/CX)

Vier verschiedene Umwandlungsoperatoren von Windows-Runtime-Typen: [Static_cast Operator](../cpp/static-cast-operator.md), [Dynamic_cast Operator](../cpp/dynamic-cast-operator.md), **Safe_cast Operator**, und [ Reinterpret_cast-Operator](../cpp/reinterpret-cast-operator.md). **"safe_cast"** und **Static_cast** löst eine Ausnahme aus, wenn die Konvertierung nicht durchgeführt werden kann; [Static_cast Operator](../cpp/static-cast-operator.md) führt außerdem die typüberprüfung zur Kompilierzeit. **Dynamic_cast** gibt **Nullptr** Ausfall den Typ konvertieren. Obwohl **Reinterpret_cast** einen Wert ungleich Null, gibt er möglicherweise ungültig. Aus diesem Grund empfehlen wir die Verwendung nicht **Reinterpret_cast** , außer Sie wissen, dass die Umwandlung erfolgreich ist. Darüber hinaus wird empfohlen, keine C-stilartige Umwandlungen zu, in die C verwenden + c++ / CX code, da sie identisch sind **Reinterpret_cast**.

Der Compiler und die Laufzeit führen ebenfalls implizite Umwandlungen aus – beispielsweise bei Boxingvorgängen, wenn ein Werttyp oder ein integrierter Datentyp als Argumente an eine Methode mit dem Parametertyp `Object^`übergeben werden. Theoretisch sollte eine implizite Umwandlung zur Laufzeit nie Ausnahmen verursachen. Wenn der Compiler eine implizite Konvertierung nicht ausführen kann, löst dies einen Fehler zur Kompilierzeit aus.

Windows-Runtime ist eine Abstraktion über COM, wodurch die HRESULT-Fehlercodes anstelle der Ausnahmen verwendet. Im Allgemeinen gibt [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) einen COM-Fehler auf niedriger Ebene bei E_NOINTERFACE an.

## <a name="staticcast"></a>static_cast

Ein **Static_cast** aktiviert ist, zum Zeitpunkt der Kompilierung zu bestimmen, ob zwischen den zwei Typen eine vererbungsbeziehung besteht. Die Umwandlung verursacht einen Compilerfehler, wenn die Typen nicht verknüpft sind.

Ein **Static_cast** auf einer Verweisklasse bewirkt auch, dass eine laufzeitüberprüfung ausgeführt werden. Ein **Static_cast** Klasse kann auf einer Verweisklasse kompilierzeitüberprüfung übergeben aber trotzdem noch fehlschlagen, zur Laufzeit; in diesem Fall eine `Platform::InvalidCastException` ausgelöst wird. Im Allgemeinen müssen Sie diese Ausnahmen nicht behandeln, da sie fast immer Programmierfehler angeben, die Sie in der Regel während der Entwicklung und der Testphase beheben können.

Verwendung **Static_cast** , wenn der Code explizit eine Beziehung zwischen den beiden Typen deklariert, und Sie aus diesem Grund Sie sicher sind, dass die Umwandlung funktioniert.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safecast"></a>safe_cast

Die **"safe_cast"** -Operator ist Teil von Windows-Runtime. Er führt eine Laufzeittypüberprüfung aus und löst `Platform::InvalidCastException` aus, wenn die Konvertierung fehlschlägt. Verwendung **"safe_cast"** Wenn ein Laufzeitfehler eine Ausnahmebedingung angibt. Der primäre Zweck von **"safe_cast"** helfen bei der Entwicklung und Testphase Phasen an der Stelle, wo sie auftreten. Sie müssen die Ausnahme nicht behandeln, da der Ausnahmefehler selbst den Fehlerpunkt identifiziert.

Verwenden Sie safe_cast, wenn der Code nicht die Beziehung deklariert, aber Sie sicher sind, dass die Umwandlung funktioniert.

```cpp
    // A and B are not related
    interface class A{};
    interface class B{};
    public ref class Class1 sealed : A, B { };
    // ...
    A^ obj = ref new Class1();

    // You know that obj’s backing type implements A and B, but
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.
    B^ obj2 = safe_cast<B^>(obj);
```

## <a name="dynamiccast"></a>dynamic_cast

Verwendung **Dynamic_cast** bei Umwandlung ein Objekts (genauer gesagt, ein Zirkumflexzeichen **^**) in einen stärker abgeleiteten Typ. Sie erwarten entweder, dass das Zielobjekt eventuell **Nullptr** oder dass die Umwandlung möglicherweise fehlschlägt, und Sie diese Bedingung in Form eines regulären Codepfads und nicht mit einer Ausnahme behandeln möchten. Z. B. in der **leere App (universelle Windows)** -Projektvorlage, die `OnLaunched` Methode bei Verwendungen temporärer Tabellen app.xamp.cpp **Dynamic_cast** zu prüfen, ob die app-Fenster über Inhalt verfügt. Es ist kein Fehler, wenn kein Inhalt vorhanden ist; es ist eine erwartete Bedingung. `Windows::Current::Content` ist ein `Windows::UI::XAML::UIElement` und die Konvertierung erfolgt in einen `Windows::UI.XAML::Controls::Frame`, der ein besser abgeleiteter Typ in der Vererbungshierarchie ist.

```cpp
void App::OnLaunched(Windows::ApplicationModel::Activation::LaunchActivatedEventArgs^ args)
{
    auto rootFrame = dynamic_cast<Frame^>(Window::Current->Content);

    // Do not repeat app initialization when the window already has content,
    // just ensure that the window is active
    if (rootFrame == nullptr)
    {
        // Create a Frame to act as the navigation context and associate it with
        // a SuspensionManager key
        rootFrame = ref new Frame();
        // ...
    }
}
```

Eine weitere Verwendungsmöglichkeit der **Dynamic_cast** ist die Überprüfung einer `Object^` um zu bestimmen, ob es sich um einen geschachtelten Werttyp enthält. In diesem Fall versuchen Sie `dynamic_cast<Platform::Box>` oder `dynamic_cast<Platform::IBox>`.

## <a name="dynamiccast-and-tracking-references-"></a>dynamic_cast und Nachverfolgungsverweise (%)

Sie können auch Anwenden einer **Dynamic_cast** auf einen Nachverfolgungsverweis, aber in diesem Fall verhält sich die Umwandlung wie **"safe_cast"**. Es wird ausgelöst, `Platform::InvalidCastException` bei einem Fehler, da ein Nachverfolgungsverweis Indexschlüsselwert kann nicht **Nullptr**.

## <a name="reinterpretcast"></a>reinterpret_cast

Es wird empfohlen, nicht [reinterpret_cast](../cpp/reinterpret-cast-operator.md) zu verwenden, da weder eine Kompilierzeitüberprüfung noch eine Laufzeitüberprüfung ausgeführt wird. Im schlimmsten Fall einen **Reinterpret_cast** ermöglicht es Programmierfehler, wechseln zur Entwicklungszeit unerkannt bleiben und subtile oder katastrophale Fehler im Programmverhalten verursachen. Deshalb wird empfohlen, die Verwendung von **Reinterpret_cast** nur in den seltenen Fällen, wenn Sie eine Umwandlung zwischen nicht verknüpften Typen müssen und Sie wissen, dass die Umwandlung erfolgt. Ein Beispiel für eine seltene Verwendung ist ein Windows-Runtime-Typen in seinem zugrunde liegenden ABI-Typ konvertiert – dies bedeutet, dass Sie übernehmen die verweiszählung für das Objekt steuern. Hierzu wird empfohlen, den intelligenten [ComPtr Class](../cpp/com-ptr-t-class.md) -Zeiger verwenden. Andernfalls müssen Sie Release auf der Schnittstelle ausdrücklich aufrufen. Das folgende Beispiel veranschaulicht, wie eine Verweisklasse zu `IInspectable*`umgewandelt werden kann.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

Bei Verwendung von **Reinterpret_cast** zum Konvertieren von OneWindows Common Language Runtime-Schnittstelle in einen anderen wird das Objekt zweimal freigegeben. Verwenden Sie daher diese Umwandlung nur, wenn Sie nicht in eine[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] -Schnittstelle konvertieren.

## <a name="abi-types"></a>ABI-Typen

- ABI-Typen befinden sich im Windows SDK in Headern. Praktischerweise sind die Header nach Namespaces benannt – z. B. `windows.storage.h`.

- ABI-Typen befinden sich in einer speziellen Namespace-ABI – z. B. `ABI::Windows::Storage::Streams::IBuffer*`.

- Konvertierungen zwischen einem Windows-Runtime--Schnittstellentyp und seinem entsprechenden ABI-Typ sind immer sicher – d. h. `IBuffer^` auf `ABI::IBuffer*`.

- Eine Windows-Runtime-Laufzeitklasse sollte immer in konvertiert werden `IInspectable*` oder ihre Standardschnittstelle, falls bekannt ist.

- Nachdem Sie die Konvertierung in ABI-Typen durchgeführt haben, verfügen Sie über die Lebensdauer des Typs und müssen den COM-Regeln folgen. Wir empfehlen zum Vereinfachen der Lebensdauerverwaltung von ABI-Zeigern, `WRL::ComPtr` zu verwenden.

Die folgende Tabelle enthält die Fälle, in denen es sicher ist **Reinterpret_cast**. In jedem Fall ist die Umwandlung in beide Richtungen sicher.

|||
|-|-|
|`HSTRING`|`String^`|
|`HSTRING*`|`String^*`|
|`IInspectable*`|`Object^`|
|`IInspectable**`|`Object^*`|
|`IInspectable-derived-type*`|`same-interface-from-winmd^`|
|`IInspectable-derived-type**`|`same-interface-from-winmd^*`|
|`IDefault-interface-of-RuntimeClass*`|`same-RefClass-from-winmd^`|
|`IDefault-interface-of-RuntimeClass**`|`same-RefClass-from-winmd^*`|

## <a name="see-also"></a>Siehe auch

- [Typsystem](../cppcx/type-system-c-cx.md)
- [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)
- [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)

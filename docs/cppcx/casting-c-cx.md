---
title: Umwandlung von Typen (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 65d489d14c91b462e5a2bbe8bd60fce2657904a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258212"
---
# <a name="casting-ccx"></a>Umwandlung von Typen (C++/CX)

Vier verschiedene Umwandlungsoperatoren von Windows-Runtime-Typen: [Static_cast-Operator](../cpp/static-cast-operator.md), [Dynamic_cast-Operator](../cpp/dynamic-cast-operator.md), **Safe_cast Operator**, und [ Reinterpret_cast-Operator](../cpp/reinterpret-cast-operator.md). **Safe_cast** und **"static_cast"** eine Ausnahme ausgelöst wird, wenn die Konvertierung kann nicht ausgeführt werden; [Static_cast-Operator](../cpp/static-cast-operator.md) führt auch die typüberprüfung zur Kompilierzeit. **Dynamic_cast** gibt **"nullptr"** bei einem Fehler, den Typ zu konvertieren. Obwohl **"reinterpret_cast"** gibt einen Wert ungleich Null, es ist möglicherweise ungültig. Aus diesem Grund wird empfohlen, dass Sie nicht verwenden, **"reinterpret_cast"** , wenn Sie wissen, dass die Umwandlung erfolgreich ist. Darüber hinaus sollten Sie keine C-stilartige Umwandlungen in Ihre C++/CX zu code, da sie identisch sind **"reinterpret_cast"**.

Der Compiler und die Laufzeit führen ebenfalls implizite Umwandlungen aus – beispielsweise bei Boxingvorgängen, wenn ein Werttyp oder ein integrierter Datentyp als Argumente an eine Methode mit dem Parametertyp `Object^`übergeben werden. Theoretisch sollte eine implizite Umwandlung zur Laufzeit nie Ausnahmen verursachen. Wenn der Compiler eine implizite Konvertierung nicht ausführen kann, löst dies einen Fehler zur Kompilierzeit aus.

Windows-Runtime ist eine Abstraktion über COM, das HRESULT-Fehlercodes anstelle der Ausnahmen verwendet. Im Allgemeinen gibt [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) einen COM-Fehler auf niedriger Ebene bei E_NOINTERFACE an.

## <a name="staticcast"></a>static_cast

Ein **"static_cast"** aktiviert ist, zum Zeitpunkt der Kompilierung zu bestimmen, ob zwischen den beiden Typen eine vererbungsbeziehung besteht. Die Umwandlung verursacht einen Compilerfehler, wenn die Typen nicht verknüpft sind.

Ein **"static_cast"** auf einer Verweisklasse bewirkt auch, dass eine laufzeitüberprüfung ausgeführt werden. Ein **"static_cast"** Klasse kann auf einer Verweisklasse kompilierzeitüberprüfung übergeben aber dennoch nicht zur Laufzeit; in diesem Fall eine `Platform::InvalidCastException` ausgelöst. Im Allgemeinen müssen Sie diese Ausnahmen nicht behandeln, da sie fast immer Programmierfehler angeben, die Sie in der Regel während der Entwicklung und der Testphase beheben können.

Verwendung **"static_cast"** Wenn der Code explizit eine Beziehung zwischen den beiden Typen deklariert, und Sie aus diesem Grund Sie sicher sind, dass die Umwandlung funktioniert.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safecast"></a>safe_cast

Die **"safe_cast"** -Operator ist Teil von Windows-Runtime. Er führt eine Laufzeittypüberprüfung aus und löst `Platform::InvalidCastException` aus, wenn die Konvertierung fehlschlägt. Verwendung **"safe_cast"** Wenn ein Laufzeitfehler eine Ausnahmebedingung angibt. Der primäre Zweck von **"safe_cast"** wird zur Identifizierung von Programmierfehlern während der Entwicklung und Testphase bei der Suche, die zum Zeitpunkt ihres Auftretens. Sie müssen die Ausnahme nicht behandeln, da der Ausnahmefehler selbst den Fehlerpunkt identifiziert.

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

Verwendung **Dynamic_cast** bei Umwandlung ein Objekts (genauer gesagt ein Caretzeichen **^**) in einen stärker abgeleiteten Typ erwarten entweder, dass das Ziel eventuell **"nullptr"** oder dass die Umwandlung möglicherweise fehlschlägt, und Sie diese Bedingung als einen regulären Codepfads und nicht mit einer Ausnahme behandeln möchten. Z. B. in der **leere App (Universelles Windows)** -Projektvorlage, die `OnLaunched` -Methode in der app.xamp.cpp verwendet **Dynamic_cast** zu prüfen, ob die app-Fenster über Inhalt verfügt. Es ist kein Fehler, wenn kein Inhalt vorhanden ist; es ist eine erwartete Bedingung. `Windows::Current::Content` ist ein `Windows::UI::XAML::UIElement` und die Konvertierung erfolgt in einen `Windows::UI.XAML::Controls::Frame`, der ein besser abgeleiteter Typ in der Vererbungshierarchie ist.

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

Sie können auch Anwenden einer **Dynamic_cast** zu einem Nachverfolgungsverweis, aber in diesem Fall verhält sich die Umwandlung wie **"safe_cast"**. Sie löst `Platform::InvalidCastException` bei einem Fehler, da ein Nachverfolgungsverweis Wert keinen **"nullptr"**.

## <a name="reinterpretcast"></a>reinterpret_cast

Es wird empfohlen, nicht [reinterpret_cast](../cpp/reinterpret-cast-operator.md) zu verwenden, da weder eine Kompilierzeitüberprüfung noch eine Laufzeitüberprüfung ausgeführt wird. Im schlimmsten Fall eine **"reinterpret_cast"** Programmierfehler unentdeckt zum Zeitpunkt der Entwicklung und subtile oder katastrophale Fehler im Programmverhalten verursachen kann. Daher wird empfohlen, dass Sie verwenden **"reinterpret_cast"** nur in den seltenen Fällen müssen Sie eine Umwandlung zwischen nicht verknüpften Typen ein, und Sie wissen, dass die Umwandlung erfolgreich ist. Ein Beispiel für eine seltene Verwendung ist, um einen Windows-Runtime-Typ in seinem zugrunde liegenden ABI-Typ zu konvertieren — Dies bedeutet, dass Sie die Kontrolle über die verweiszählung für das Objekt vorliegen. Hierzu wird empfohlen, den intelligenten [ComPtr Class](../cpp/com-ptr-t-class.md) -Zeiger verwenden. Andernfalls müssen Sie Release auf der Schnittstelle ausdrücklich aufrufen. Das folgende Beispiel veranschaulicht, wie eine Verweisklasse zu `IInspectable*`umgewandelt werden kann.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

Bei Verwendung von **"reinterpret_cast"** um von OneWindows-Runtime-Schnittstelle in eine andere zu konvertieren, wird das Objekt zweimal freigegeben werden. Nur verwenden Sie daher diese Umwandlung, wenn Sie in einer nicht - Visual C++-Erweiterungen Komponentenschnittstelle konvertieren.

## <a name="abi-types"></a>ABI-Typen

- ABI-Typen befinden sich im Windows SDK in Headern. Praktischerweise sind die Header nach Namespaces benannt – z. B. `windows.storage.h`.

- ABI-Typen befinden sich in einer speziellen Namespace-ABI – z. B. `ABI::Windows::Storage::Streams::IBuffer*`.

- Konvertierungen zwischen einem Windows-Runtime-Schnittstelle und seinem entsprechenden ABI-Typ sind immer sicher – d. h. `IBuffer^` zu `ABI::IBuffer*`.

- Eine Windows-Runtime-Runtime-Klasse sollte immer in konvertiert werden `IInspectable*` oder ihre Standardschnittstelle, falls bekannt ist.

- Nachdem Sie die Konvertierung in ABI-Typen durchgeführt haben, verfügen Sie über die Lebensdauer des Typs und müssen den COM-Regeln folgen. Wir empfehlen zum Vereinfachen der Lebensdauerverwaltung von ABI-Zeigern, `WRL::ComPtr` zu verwenden.

Die folgende Tabelle enthält die Fälle, in dem gefahrlos verwenden **"reinterpret_cast"**. In jedem Fall ist die Umwandlung in beide Richtungen sicher.

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
- [Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)
- [Referenz zu Namespaces](../cppcx/namespaces-reference-c-cx.md)

---
title: Umwandlung von Typen (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 6711320fd9ca52360f702e029fdc8e129c90c6cd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740538"
---
# <a name="casting-ccx"></a>Umwandlung von Typen (C++/CX)

Vier verschiedene Umwandlungs Operatoren gelten für Windows-Runtime Typen: [static_cast-Operator](../cpp/static-cast-operator.md), [dynamic_cast](../cpp/dynamic-cast-operator.md)-Operator, **safe_cast-Operator**und reinterpret_cast- [Operator](../cpp/reinterpret-cast-operator.md). **safe_cast** und **static_cast** lösen eine Ausnahme aus, wenn die Konvertierung nicht ausgeführt werden kann. der [static_cast-Operator](../cpp/static-cast-operator.md) führt außerdem eine Typüberprüfung zur Kompilierzeit durch. **dynamic_cast** gibt **nullptr** zurück, wenn der Typ nicht konvertiert werden kann. Obwohl **reinterpret_cast** einen nicht-NULL-Wert zurückgibt, ist er möglicherweise ungültig. Aus diesem Grund wird empfohlen, **reinterpret_cast** nur dann zu verwenden, wenn Sie wissen, dass die Umwandlung erfolgreich ist. Außerdem wird empfohlen, dass Sie keine Umwandlungen im C-Stil in Ihrem C++/CX-Code verwenden, da Sie mit **reinterpret_cast**identisch sind.

Der Compiler und die Laufzeit führen ebenfalls implizite Umwandlungen aus – beispielsweise bei Boxingvorgängen, wenn ein Werttyp oder ein integrierter Datentyp als Argumente an eine Methode mit dem Parametertyp `Object^`übergeben werden. Theoretisch sollte eine implizite Umwandlung zur Laufzeit nie Ausnahmen verursachen. Wenn der Compiler eine implizite Konvertierung nicht ausführen kann, löst dies einen Fehler zur Kompilierzeit aus.

Windows-Runtime ist eine Abstraktion über com, bei der HRESULT-Fehlercodes anstelle von Ausnahmen verwendet werden. Im Allgemeinen gibt [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) einen COM-Fehler auf niedriger Ebene bei E_NOINTERFACE an.

## <a name="static_cast"></a>static_cast

Ein **static_cast** wird zum Zeitpunkt der Kompilierung geprüft, um zu bestimmen, ob zwischen den beiden Typen eine Vererbungs Beziehung besteht. Die Umwandlung verursacht einen Compilerfehler, wenn die Typen nicht verknüpft sind.

Ein **static_cast** für eine Verweis Klasse bewirkt auch, dass eine Lauf Zeit Überprüfung ausgeführt wird. Ein **static_cast** -Verweis auf eine Verweis Klasse kann die Kompilierzeit Überprüfung bestehen, kann aber zur Laufzeit weiterhin fehlschlagen. in diesem Fall wird `Platform::InvalidCastException` eine ausgelöst. Im Allgemeinen müssen Sie diese Ausnahmen nicht behandeln, da sie fast immer Programmierfehler angeben, die Sie in der Regel während der Entwicklung und der Testphase beheben können.

Verwenden Sie **static_cast** , wenn der Code explizit eine Beziehung zwischen den beiden Typen deklariert und Sie daher sicher sind, dass die Umwandlung funktioniert.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safe_cast"></a>safe_cast

Der **safe_cast** -Operator ist Teil Windows-Runtime. Er führt eine Laufzeittypüberprüfung aus und löst `Platform::InvalidCastException` aus, wenn die Konvertierung fehlschlägt. Verwenden Sie **safe_cast** , wenn ein Laufzeitfehler eine Ausnahme Bedingung angibt. Der Hauptzweck von **safe_cast** ist die Identifizierung von Programmierfehlern während der Entwicklungs-und Testphasen an dem Punkt, an dem Sie auftreten. Sie müssen die Ausnahme nicht behandeln, da der Ausnahmefehler selbst den Fehlerpunkt identifiziert.

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

## <a name="dynamic_cast"></a>dynamic_cast

Verwenden Sie **dynamic_cast** Wenn Sie ein Objekt (genauer gesagt, einen hat **^** ) in einen stärker abgeleiteten Typ umwandeln, erwarten Sie, dass das Zielobjekt manchmal **nullptr** ist oder dass bei der Umwandlung ein Fehler auftritt, und Sie möchten diese Bedingung als regulärer Codepfad anstelle einer Ausnahme. Beispielsweise verwendet die `OnLaunched` -Methode in "App. xamp. cpp" in der Projektvorlage " **leere app" (universelle Windows-APP)** **dynamic_cast** , um zu testen, ob das App-Fenster über Inhalt verfügt. Es ist kein Fehler, wenn kein Inhalt vorhanden ist; es ist eine erwartete Bedingung. `Windows::Current::Content` ist ein `Windows::UI::XAML::UIElement` und die Konvertierung erfolgt in einen `Windows::UI.XAML::Controls::Frame`, der ein besser abgeleiteter Typ in der Vererbungshierarchie ist.

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

Eine weitere Verwendung von **dynamic_cast** besteht darin, `Object^` einen zu überprüfen, um zu bestimmen, ob er einen gescanchten Werttyp enthält In diesem Fall versuchen Sie `dynamic_cast<Platform::Box>` oder `dynamic_cast<Platform::IBox>`.

## <a name="dynamic_cast-and-tracking-references-"></a>dynamic_cast und Nachverfolgungsverweise (%)

Sie können auch ein **dynamic_cast** auf einen nach Verfolgungs Verweis anwenden, aber in diesem Fall verhält sich die Umwandlung wie **safe_cast**. Sie löst bei einem Fehler eine aus, da ein nach Verfolgungs Verweis keinen Wert von **nullptr**aufweisen kann. `Platform::InvalidCastException`

## <a name="reinterpret_cast"></a>reinterpret_cast

Es wird empfohlen, nicht [reinterpret_cast](../cpp/reinterpret-cast-operator.md) zu verwenden, da weder eine Kompilierzeitüberprüfung noch eine Laufzeitüberprüfung ausgeführt wird. Im ungünstigsten Fall ermöglicht ein **reinterpret_cast** , dass Programmierfehler zur Entwicklungszeit nicht erkannt werden und zu geringfügigen oder schwerwiegenden Fehlern im Verhalten des Programms führen. Daher wird empfohlen, **reinterpret_cast** nur in den seltenen Fällen zu verwenden, wenn Sie eine Umwandlung zwischen nicht verknüpften Typen durchführen müssen und Sie wissen, dass die Umwandlung erfolgreich ist. Ein Beispiel für eine seltene Verwendung ist das Konvertieren eines Windows-Runtime Typs in den zugrunde liegenden ABI-Typ – Dies bedeutet, dass Sie die Verweis Zählung für das Objekt übernehmen. Hierzu wird empfohlen, den intelligenten [ComPtr Class](../cpp/com-ptr-t-class.md) -Zeiger verwenden. Andernfalls müssen Sie Release auf der Schnittstelle ausdrücklich aufrufen. Das folgende Beispiel veranschaulicht, wie eine Verweisklasse zu `IInspectable*`umgewandelt werden kann.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

Wenn Sie **reinterpret_cast** verwenden, um von der onewindows-Runtime-Schnittstelle in eine andere zu konvertieren, wird das Objekt zweimal freigegeben. Verwenden Sie daher diese Umwandlung nur, wenn Sie eine Schnittstelle für eineC++ nicht-Komponenten Erweiterung konvertieren.

## <a name="abi-types"></a>ABI-Typen

- ABI-Typen befinden sich im Windows SDK in Headern. Praktischerweise sind die Header nach Namespaces benannt – z. B. `windows.storage.h`.

- ABI-Typen befinden sich in einer speziellen Namespace-ABI – z. B. `ABI::Windows::Storage::Streams::IBuffer*`.

- Konvertierungen zwischen einem Windows-Runtime Schnittstellentyp und seinem entsprechenden ABI-Typ sind immer sicher – `IBuffer^` d `ABI::IBuffer*`. h. auf.

- Eine Windows-Runtime Lauf Zeit Klasse sollte immer in `IInspectable*` oder Ihre Standardschnittstelle konvertiert werden, wenn dies bekannt ist.

- Nachdem Sie die Konvertierung in ABI-Typen durchgeführt haben, verfügen Sie über die Lebensdauer des Typs und müssen den COM-Regeln folgen. Wir empfehlen zum Vereinfachen der Lebensdauerverwaltung von ABI-Zeigern, `WRL::ComPtr` zu verwenden.

In der folgenden Tabelle werden die Fälle zusammengefasst, in denen die Verwendung von **reinterpret_cast**sicher ist. In jedem Fall ist die Umwandlung in beide Richtungen sicher.

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
- [C++-/CX-Programmiersprachenreferenz](../cppcx/visual-c-language-reference-c-cx.md)
- [Referenz zu Namespaces](../cppcx/namespaces-reference-c-cx.md)

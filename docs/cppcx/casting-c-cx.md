---
title: Umwandlung von Typen (C + c++ / CX) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f71be537ecc0dc0cb58a3ada13612dbe8cbd7d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="casting-ccx"></a>Umwandlung von Typen (C++/CX)
Vier verschiedene Umwandlungsoperatoren von Windows-Runtime-Typen: [Static_cast Operator](../cpp/static-cast-operator.md), [Dynamic_cast Operator](../cpp/dynamic-cast-operator.md), **Safe_cast Operator**, und [ Reinterpret_cast-Operator](../cpp/reinterpret-cast-operator.md). `safe_cast` und `static_cast` lösen eine Ausnahme aus, wenn die Umwandlung nicht ausgeführt werden kann; der Operator [static_cast](../cpp/static-cast-operator.md) führt außerdem bei der Kompilierung eine Typprüfung durch. `dynamic_cast` gibt `nullptr` zurück, wenn der Typ nicht umgewandelt werden kann. Obwohl `reinterpret_cast` einen Wert ungleich Null zurückgibt, ist er möglicherweise ungültig. Aus diesem Grund wird empfohlen, dass Sie `reinterpret_cast` nur verwenden, wenn Sie wissen, dass die Umwandlung folgt. Darüber hinaus wird empfohlen, keine C-stilartige Umwandlungen zu, in die C verwenden + c++ / CX code, da sie identisch sind `reinterpret_cast`.  
  
 Der Compiler und die Laufzeit führen ebenfalls implizite Umwandlungen aus – beispielsweise bei Boxingvorgängen, wenn ein Werttyp oder ein integrierter Datentyp als Argumente an eine Methode mit dem Parametertyp `Object^`übergeben werden. Theoretisch sollte eine implizite Umwandlung zur Laufzeit nie Ausnahmen verursachen. Wenn der Compiler eine implizite Konvertierung nicht ausführen kann, löst dies einen Fehler zur Kompilierzeit aus.  
  
Windows-Runtime ist eine Abstraktion über COM, wodurch die HRESULT-Fehlercodes anstelle der Ausnahmen verwendet. Im Allgemeinen gibt [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) einen COM-Fehler auf niedriger Ebene bei E_NOINTERFACE an.  
  
## <a name="staticcast"></a>static_cast  
 `static_cast` wird zur Kompilierzeit überprüft, um zu bestimmen, ob zwischen den zwei Typen eine Vererbungsbeziehung besteht. Die Umwandlung verursacht einen Compilerfehler, wenn die Typen nicht verknüpft sind.  
  
 Ein `static_cast` auf einer Verweisklasse bewirkt auch, dass eine Laufzeitüberprüfung ausgeführt wird. `static_cast` kann auf einer Verweisklasse Kompilierzeitüberprüfung übergeben aber weiterhin einen Fehler zur Laufzeit verursachen. In diesem Fall wird `Platform::InvalidCastException` ausgelöst. Im Allgemeinen müssen Sie diese Ausnahmen nicht behandeln, da sie fast immer Programmierfehler angeben, die Sie in der Regel während der Entwicklung und der Testphase beheben können.  
  
 Verwenden Sie `static_cast` , wenn der Code explizit eine Beziehung zwischen den beiden Typen deklariert. Daher können Sie sicher sein, dass die Umwandlung funktioniert.  
  
```
    interface class A{};  
    public ref class Class1 sealed : A { };  
...  
    A^ obj = ref new Class1(); // Class1 is an A  
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.  
    Class1^ c = static_cast<Class1^>(obj);
```  
  
## <a name="safecast"></a>safe_cast  
 Die `safe_cast` -Operator ist Teil mit Windows Runtime. Er führt eine Laufzeittypüberprüfung aus und löst `Platform::InvalidCastException` aus, wenn die Konvertierung fehlschlägt. Verwenden Sie `safe_cast` , wenn ein Laufzeitfehler eine Ausnahmebedingung angibt. `safe_cast` soll hauptsächlich während der Entwicklung und Testphase bei der Suche nach Programmierfehlern am Punkt ihres Auftretens helfen. Sie müssen die Ausnahme nicht behandeln, da der Ausnahmefehler selbst den Fehlerpunkt identifiziert.  
  
 Verwenden Sie safe_cast, wenn der Code nicht die Beziehung deklariert, aber Sie sicher sind, dass die Umwandlung funktioniert.  
  
```  
    // A and B are not related  
    interface class A{};  
    interface class B{};  
    public ref class Class1 sealed : A, B { };  
...  
    A^ obj = ref new Class1();  
  
    // You know that obj’s backing type implements A and B, but  
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.  
    B^ obj2 = safe_cast<B^>(obj);  
```  
  
## <a name="dynamiccast"></a>dynamic_cast  
 Verwendung `dynamic_cast` bei Umwandlung ein Objekts (genauer gesagt, ein Zirkumflexzeichen `^`) in einen stärker abgeleiteten Typ. Sie erwarten entweder, dass das Zielobjekt eventuell `nullptr` oder dass die Umwandlung möglicherweise fehlschlägt, und Sie sollten diese Bedingung als reguläre Code behandeln der Pfad nicht mit einer Ausnahme. Beispielsweise ist in der **leere App (universelle Windows)** Projektvorlage für Startseiten, die `OnLaunched` Methode in `app.xamp.cpp` verwendet `dynamic_cast` zu prüfen, ob die app-Fenster über Inhalt verfügt. Es ist kein Fehler, wenn kein Inhalt vorhanden ist; es ist eine erwartete Bedingung. `Windows::Current::Content` ist ein `Windows::UI::XAML::UIElement` und die Konvertierung erfolgt in einen `Windows::UI.XAML::Controls::Frame`, der ein besser abgeleiteter Typ in der Vererbungshierarchie ist.  
```
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
...  
```  
 Eine andere Verwendung von `dynamic_cast` ist die Überprüfung von einem `Object^` , um zu bestimmen, ob es einen geschachtelten Werttyp enthält. In diesem Fall versuchen Sie `dynamic_cast<Platform::Box>` oder `dynamic_cast<Platform::IBox>`.  
  
 **dynamic_cast und Nachverfolgungsverweise (%)**  
  
 Sie können `dynamic_cast` auch auf einen Nachverfolgungsverweis anwenden. In diesem Fall verhält sich die Umwandlung wie `safe_cast`. Sie löst bei einem Fehler eine `Platform::InvalidCastException` aus, da ein Nachverfolgungsverweis keinen Wert von `nullptr`aufweisen kann.  
  
## <a name="reinterpretcast"></a>reinterpret_cast  
 Es wird empfohlen, nicht [reinterpret_cast](../cpp/reinterpret-cast-operator.md) zu verwenden, da weder eine Kompilierzeitüberprüfung noch eine Laufzeitüberprüfung ausgeführt wird. Im schlimmsten Fall können Programmierfehler mit einem `reinterpret_cast` zur Entwicklungszeit unerkannt bleiben und subtile oder katastrophale Fehler im Programmverhalten verursachen. Daher empfehlen wir, `reinterpret_cast` nur in den seltenen Fällen zu verwenden, wenn Sie eine Umwandlung zwischen nicht verknüpften Typen vornehmen müssen und Sie wissen, dass die Umwandlung erfolgt. Ein Beispiel für eine seltene Verwendung ist, um eine Windows-Runtime-Typ in seinem zugrunde liegenden ABI-Typ zu konvertieren – Dies bedeutet, dass Sie übernehmen die verweiszählung für das Objekt steuern. Hierzu wird empfohlen, den intelligenten [ComPtr Class](../cpp/com-ptr-t-class.md) -Zeiger verwenden. Andernfalls müssen Sie Release auf der Schnittstelle ausdrücklich aufrufen. Das folgende Beispiel veranschaulicht, wie eine Verweisklasse zu `IInspectable*`umgewandelt werden kann.  
  
```  
#include <wrl.h>  
using namespace Microsoft::WRL;  
auto winRtObject = ref new SomeWinRTType();  
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);  
...
```  
  
 Bei Verwendung von `reinterpret_cast` zum Konvertieren von OneWindows Common Language Runtime-Schnittstelle in einen anderen wird das Objekt zweimal freigegeben. Verwenden Sie daher diese Umwandlung nur, wenn Sie nicht in eine[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] -Schnittstelle konvertieren.  
  
 **ABI-Typen**  
  
-   ABI-Typen befinden sich im Windows SDK in Headern. Praktischerweise sind die Header nach Namespaces benannt – z. B. `windows.storage.h`.  
  
-   ABI-Typen befinden sich in einer speziellen Namespace-ABI – z. B. `ABI::Windows::Storage::Streams::IBuffer*`.  
  
-   Konvertierungen zwischen eine Windows-Runtime--Schnittstellentyp und seinem entsprechenden ABI-Typ sind immer sicher – d. h. `IBuffer^` auf `ABI::IBuffer*`.  
  
-   AWindows Runtime, Runtime-Klasse sollte immer konvertiert werden, um `IInspectable*` oder ihre Standardschnittstelle, falls bekannt ist.  
  
-   Nachdem Sie die Konvertierung in ABI-Typen durchgeführt haben, verfügen Sie über die Lebensdauer des Typs und müssen den COM-Regeln folgen. Wir empfehlen zum Vereinfachen der Lebensdauerverwaltung von ABI-Zeigern, `WRL::ComPtr` zu verwenden.  
  
 In der folgenden Tabelle werden die Fälle aufgeführt, in denen es sicher ist, `reinterpret_cast`zu verwenden. In jedem Fall ist die Umwandlung in beide Richtungen sicher.  
  
|||  
|-|-|  
|HSTRING|String^|  
|HSTRING*|String^*|  
|IInspectable*|Object^|  
|IInspectable**|Object^*|  
|IInspectable-derived-type*|same-interface-from-winmd^|  
|IInspectable-derived-type**|same-interface-from-winmd^*|  
|IDefault-interface-of-RuntimeClass*|same-RefClass-from-winmd^|  
|IDefault-interface-of-RuntimeClass**|same-RefClass-from-winmd^*|  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Visual C++-Sprachreferenz](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)

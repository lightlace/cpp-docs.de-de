---
title: 'Vorgehensweise: Aktivieren und verwenden Sie eine Windows-Runtime-Komponente mit WRL | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c430ca0dd63c4cbe46986147617ccbd752597ab
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Gewusst wie: Aktivieren und Verwenden einer Windows-Runtime-Komponente mit WRL
Dieses Dokument wird gezeigt, wie die Windows Runtime C++ Template Library (WRL) verwenden, um die Windows-Runtime zu initialisieren und zu aktivieren und verwenden eine Windows-Runtime-Komponente.  
  
 Um eine Komponente zu verwenden, müssen Sie einen Schnittstellenzeiger auf den Typ abrufen, der von der Komponente implementiert wird. Und da die zugrunde liegende Technologie der Windows-Runtime das Component Object Model (COM) ist, müssen Sie die COM-Regeln, um eine Instanz des Typs beizubehalten entsprechen. Sie müssen z. B. verwalten die *Verweiszähler* , der bestimmt, wenn der Typ aus dem Arbeitsspeicher gelöscht wird.  
  
 Um die Verwendung von Windows-Runtime zu vereinfachen, stellt Windows Runtime C++ Template Library die Vorlage intelligenten Zeiger [ComPtr\<T >](../windows/comptr-class.md), verweiszählung, die automatisch ausgeführt. Wenn Sie eine Variable deklarieren, geben Sie `ComPtr<` *Schnittstellenname* `>` *Bezeichner*. Um auf einen Schnittstellenmember zuzugreifen, wenden Sie den Pfeilmemberzugriffsoperator (`->`) auf den Bezeichner an.  
  
> [!IMPORTANT]
>  Wenn Sie eine Schnittstellenfunktion aufrufen, testen Sie stets den Rückgabewert `HRESULT`.  
  
## <a name="activating-and-using-a-windows-runtime-component"></a>Aktivieren und Verwenden einer Windows Runtime-Komponente  
 Die folgenden Schritte verwenden den `Windows::Foundation::IUriRuntimeClass` Schnittstelle zu veranschaulichen, wie Sie eine aktivierungsfactory für eine Windows-Runtime-Komponente erstellen, erstellen Sie eine Instanz dieser Komponente und Abrufen eines Eigenschaftswerts. Außerdem wird gezeigt, wie die Windows-Runtime initialisiert. Im Folgenden finden Sie das vollständige Beispiel.  
  
> [!IMPORTANT]
>  Obwohl Sie in der Regel die Windows Runtime C++ Template Library in einer app (Universelle Windows Plattform) verwenden, wird in diesem Beispiel eine Konsolen-app zur Veranschaulichung verwendet. Funktionen wie `wprintf_s` stehen nicht aus einer uwp-app. Weitere Informationen zu den Typen und Funktionen, die Sie in einer uwp-app verwenden können, finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) und [Win32 und COM für uwp-apps](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
#### <a name="to-activate-and-use-a-windows-runtime-component"></a>So aktivieren und verwenden Sie eine Windows Runtime-Komponente  
  
1.  Einschließen (`#include`) alle erforderlichen Windows-Runtime, C++-Vorlagenbibliothek für Windows-Runtime oder C++-Standardbibliothek-Header.  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     Es wird empfohlen, den Code mithilfe der `using namespace`-Direktive in der CPP-Datei verständlicher zu gestalten.  
  
2.  Initialisieren Sie den Thread, in dem die App ausgeführt wird. Jede App muss ihren Thread und ihr Threadingmodell initialisieren. Dieses Beispiel verwendet die [Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md) -Klasse zum Initialisieren der Windows-Runtime und gibt [RO_INIT_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) als Threadingmodell. Die `RoInitializeWrapper`-Klasse ruft `Windows::Foundation::Initialize` auf, wenn sie erstellt, und `Windows::Foundation::Uninitialize`, wenn sie zerstört wird.  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     In der zweiten Anweisung wird die [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) Operator gibt den `HRESULT` im Aufruf von `Windows::Foundation::Initialize`.  
  
3.  Erstellen einer *aktivierungsfactory* für die `ABI::Windows::Foundation::IUriRuntimeClassFactory` Schnittstelle.  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     Windows-Runtime verwendet den vollqualifizierten Namen zum Identifizieren von Typen. Die `RuntimeClass_Windows_Foundation_Uri` Parameter ist eine Zeichenfolge, die vom Windows-Runtime bereitgestellt wird und den erforderlichen ablaufklassennamen enthält.  
  
4.  Initialisieren einer [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) Variable, die den URI darstellt `"http://www.microsoft.com"`.  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     In der Windows-Runtime nicht Sie nach einer Zeichenfolge belegt werden, die Windows-Runtime verwendet werden. Stattdessen erstellt die Windows-Runtime eine Kopie der Zeichenfolge in einem Puffer, die er verwaltet und für Vorgänge verwendet, und gibt ein Handle auf den Puffer, dass sie erstellt.  
  
5.  Erstellen Sie mit der `IUriRuntimeClassFactory::CreateUri`-Factorymethode ein `ABI::Windows::Foundation::IUriRuntimeClass`-Objekt.  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  Rufen Sie die `IUriRuntimeClass::get_Domain`-Methode auf, um den Wert der `Domain`-Eigenschaft abzurufen.  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  Drucken Sie den Domänennamen an die Konsole, und kehren Sie zurück. Alle `ComPtr`- und RAII-Objekte verlassen den Bereich und werden automatisch freigegeben.  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     Die [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) Funktion ruft die zugrunde liegenden Unicode-Format der URI-Zeichenfolge ab.  
  
 Im Folgenden sehen Sie das vollständige Beispiel:  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `wrl-consume-component.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe wrl-consume-component.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Vorlagenbibliothek für Windows-Runtime (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)
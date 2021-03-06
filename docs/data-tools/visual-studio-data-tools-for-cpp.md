---
title: Visual Studio tools danych dla języka C++
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CPP
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
- cplusplus
ms.openlocfilehash: fe50ecd01b8f3112340510a78f76d6e380ec3136
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117033"
---
# <a name="visual-studio-data-tools-for-c"></a>Visual Studio tools danych dla języka C++

Natywnych języka C++ często zapewnia największą wydajność, gdy uzyskujesz dostęp do źródła danych. Jednak dane narzędzi dla aplikacji w języku C++ w programie Visual Studio nie jest w głębokiej, podobnie jak w przypadku aplikacji .NET. Na przykład windows źródeł danych nie może służyć do przeciągania i upuszczania źródeł danych na powierzchnię projektu C++. Warstwa obiektów relacyjnych należy należy napisać własny lub użyj innej firmy.  To samo dotyczy funkcji wiązania danych, mimo że aplikacje korzystające z biblioteki Microsoft Foundation klasy można używać niektórych klas baz danych, wraz z dokumentami i widokami, przechowywanie danych w pamięci i wyświetlić je użytkownikowi. Aby uzyskać więcej informacji, zobacz [dostęp do danych w programie Visual C++](/cpp/data/data-access-in-cpp).

Aby nawiązać połączenie bazy danych SQL, natywnych aplikacji C++ można użyć sterowników ODBC i OLE DB i dostawcy ADO, które są dołączone do systemu Windows. Te można połączyć się z dowolnej bazy danych, która obsługuje te interfejsy. Sterownik ODBC jest standardowym. OLE DB jest dostępne w celu zgodności z poprzednimi wersjami. Aby uzyskać więcej informacji dotyczących tych technologii danych, zobacz [Windows Data Access Components](https://msdn.microsoft.com/library/windows/desktop/aa968814.aspx).

Aby móc korzystać z funkcji niestandardowych w programie SQL Server 2005 i nowszym, użyj [SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client). Aplikacja native client zawiera także sterownik ODBC programu SQL Server i SQL Server dostawcy OLE DB w jednej macierzystej dynamicznej biblioteki dołączanej (dynamicznie DLL). Obsługują one aplikacji za pomocą API kodu macierzystego (ODBC, OLE DB i ADO) do programu Microsoft SQL Server.  Instaluje program SQL Server Native Client z programu SQL Server Data Tools. Podręcznik programowania jest tutaj: [programu SQL Server Native klienta programowania](/sql/relational-databases/native-client/sql-server-native-client-programming).

## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>Aby nawiązać połączenie localDB za pośrednictwem ODBC i SQL Native Client z poziomu aplikacji w języku C++

1.  Zainstaluj program SQL Server Data Tools.

2.  Przykładowa baza danych SQL do nawiązania połączenia, należy pobrać bazy danych Northwind i Rozpakuj go do nowej lokalizacji.

3.  Dołączyć rozpakowane za pomocą programu SQL Server Management Studio *Northwind.mdf* pliku do localDB. Po uruchomieniu programu SQL Server Management Studio połącz się (localdb) \MSSQLLocalDB.

     ![Okno dialogowe Połącz SSMS](../data-tools/media/raddata-ssms-connect-dialog.png)

     Kliknij prawym przyciskiem myszy w węźle localdb w okienku po lewej stronie i wybierz polecenie **Attach**.

     ![SSMS dołączyć bazy danych](../data-tools/media/raddata-ssms-attach-database.png)

4.  Pobierz przykład zestawu SDK systemu Windows ODBC i Rozpakuj go do nowej lokalizacji. W tym przykładzie przedstawiono podstawowe polecenia ODBC, które są używane do połączenia z bazą danych i problem zapytań i poleceń. Dowiedz się więcej o tych funkcji w [Otwórz połączenie bazy danych (ODBC) firmy Microsoft](/sql/odbc/microsoft-open-database-connectivity-odbc). Podczas ładowania najpierw rozwiązania (jest w folderze C++), programu Visual Studio oferuje Uaktualnij rozwiązanie do bieżącej wersji programu Visual Studio. Kliknij przycisk **Tak**.

5.  Aby użyć natywnego klienta, należy jej *nagłówka* pliku i *lib* pliku. Te pliki zawierają funkcje i definicje charakterystyczne dla programu SQL Server poza funkcji ODBC zdefiniowanych w sql.h. W **projektu** > **właściwości** > **katalogi VC ++**, Dodaj katalog dołączania następujące:

**%ProgramFiles%\Microsoft SQL Server\110\SDK\Include**

I ten katalog biblioteki:

**%ProgramFiles%\Microsoft SQL Server\110\SDK\Lib**

6.  Dodaj następujące wiersze do *odbcsql.cpp*. #Define uniemożliwia kompilowany nie znaczenia definicji OLE DB.

    ```cpp
    #define _SQLNCLI_ODBC_
    #include <sqlncli.h>
    ```

    Należy pamiętać, że próbki nie faktycznie funkcjonalności klienta natywnej, poprzednie kroki nie są niezbędne, aby skompilować i uruchomić. Ale projektu jest skonfigurowany do użycia tej funkcji. Aby uzyskać więcej informacji, zobacz [programowania w języku SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client).

7.  Określ, który sterownik do użycia w podsystemie ODBC. Przykład przekazuje atrybut parametrów połączenia sterownika w jako argument wiersza polecenia. W **projektu** > **właściwości** > **debugowanie**, Dodaj ten argument polecenia:

    ```cpp
    DRIVER="SQL Server Native Client 11.0"
    ```

8.  Naciśnij klawisz **F5** Aby skompilować i uruchomić aplikację. Powinny pojawić okno dialogowe w sterowniku wyświetli monit o wprowadzenie bazy danych. Wprowadź `(localdb)\MSSQLLocalDB`i sprawdź **Użyj zaufanego połączenia**. Naciśnij klawisz **OK**. Powinna zostać wyświetlona konsola z komunikatów, które wskazują udane połączenie. Należy również sprawdzić wiersza polecenia można wpisać w instrukcji SQL. Poniższym ekranie przedstawiono przykładowe zapytanie i wyniki:

     ![ODBC przykładowe zapytanie dane wyjściowe](../data-tools/media/raddata-odbc-sample-query-output.png)

## <a name="see-also"></a>Zobacz także

- [Uzyskiwanie dostępu do danych w programie Visual Studio](../data-tools/accessing-data-in-visual-studio.md)
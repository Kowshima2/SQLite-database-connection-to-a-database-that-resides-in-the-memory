# SQLite-database-connection-to-a-database-that-resides-in-the-memory
import sqlite3

try:
    
    conn = sqlite3.connect(':memory:')
    print("\nMemory database created and connected to SQLite.")

    sqlite_select_Query = "select sqlite_version();"
    cursor = conn.cursor()
    cursor.execute(sqlite_select_Query)

    record = cursor.fetchall()
    print("\nSQLite Database Version is:", record)

    cursor.close()

except sqlite3.Error as error:
    print("\nError while connecting to sqlite", error)

finally:
    if conn:
        conn.close()
        print("\nThe SQLite connection is closed.")
 output:
 Memory database created and connected to SQLite.

SQLite Database Version is: [('3.50.4',)]

The SQLite connection is closed.

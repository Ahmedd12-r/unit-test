import unittest
from bank import BankAccount

class TestBank(unittest.TestCase):
    def test_deposit(self):
        account = BankAccount("Ahmed", 0)
        account.deposit(100)
        self.assertEqual(account.get_balance(), 100)

    def test_deposit_error(self):
        account = BankAccount("Ahned", 0)
        with self.assertRaises(ValueError):
            account.deposit(-50)
    def test_withdraw(self):
        account = BankAccount("Ahmed", 100)
        account.withdraw(30)
        self.assertEqual(account.get_balance(), 70)

    def test_withdraw_error(self):
        account = BankAccount("Ahmed", 100)
        with self.assertRaises(ValueError):
            account.withdraw(150)

    def test_get_balance(self):
        account = BankAccount("Ahmed", 200)
        self.assertEqual(account.get_balance(), 200)
          

if __name__ == '__main__':
    unittest.main() 
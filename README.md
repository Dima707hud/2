# 2class SuitcaseLock:
    def __init__(self, combination):
        self.combination = combination
        self.is_locked = True
    
    def lock(self):
        self.is_locked = True
        print("The suitcase is now locked.")
    
    def unlock(self, combination):
        if combination == self.combination:
            self.is_locked = False
            print("The suitcase is now unlocked.")
        else:
            print("Incorrect combination. The suitcase remains locked.")
    
    def change_combination(self, new_combination):
        self.combination = new_combination
        print("The combination has been changed.")

# Example usage
lock = SuitcaseLock("1234")
lock.unlock("0000")  # Should fail, incorrect combination
lock.unlock("1234")  # Should succeed, correct combination
lock.lock()
lock.change_combination("5678")  # Change combination
lock.unlock("1234")  # Should fail, old combination
lock.unlock("5678")  # Should succeed, new combination

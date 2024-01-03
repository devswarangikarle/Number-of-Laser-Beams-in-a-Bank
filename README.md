# Number-of-Laser-Beams-in-a-Bank

class Solution:
    def numberOfBeams(self, bank):
        prev_row_count = 0
        total = 0

        for row in bank:
           
            cur_row_count = self.calculate_security_count(row)

          
            if cur_row_count == 0:
                continue

          
            total += cur_row_count * prev_row_count

           
            prev_row_count = cur_row_count

        return total

    def calculate_security_count(self, s):
        return sum(int(c) for c in s)

# Example usage:
bank1 = ["011001", "000000", "010100", "001000"]
print(Solution().numberOfBeams(bank1))  

bank2 = ["000", "111", "000"]
print(Solution().numberOfBeams(bank2))

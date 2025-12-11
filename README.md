# monthly_snapshot
# --- Monthly snapshot + side hustle calculator (interactive) ---

# Ask the user for their numbers instead of hardcoding
monthly_income = float(input("Enter your monthly after-tax income: "))
monthly_expenses = float(input("Enter your total monthly expenses: "))
target_investing = float(input("Enter your target monthly investing amount: "))

def monthly_savings(income, expenses):
    return income - expenses

def needed_side_hustle(target, base_savings):
    gap = target - base_savings
    return max(0, gap)

base_savings = monthly_savings(monthly_income, monthly_expenses)
side_hustle_needed = needed_side_hustle(target_investing, base_savings)

print("\n=== Monthly Financial Snapshot ===")
print(f"Income:            ${monthly_income}")
print(f"Expenses:          ${monthly_expenses}")
print(f"Base savings:      ${base_savings}")
print(f"Target investing:  ${target_investing}")

if side_hustle_needed == 0:
    print("\nYou're already meeting your investing target with your main income.")
else:
    print(f"\nYou need about ${side_hustle_needed} per month from side hustles to hit your target.")

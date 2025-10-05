# lot-size-calculator-for-xau-usd
def calculate_lot_size(balance: float, risk_percent: float, stop_loss_pips: float) -> float:
    pip_value_per_lot = 1
    risk_amount = balance * (risk_percent / 100)
    lot_size = risk_amount / (stop_loss_pips * pip_value_per_lot)
    return lot_size


def main():
    print("=== XAUUSD Lot Size Calculator ===\n")
    try:
        balance = float(input("Enter account balance ($): "))
        risk_percent = float(input("Enter risk percentage (%): "))
        stop_loss_pips = float(input("Enter stop loss (in pips): "))
        lot = calculate_lot_size(balance, risk_percent, stop_loss_pips)
        print(f"\nRecommended lot size for XAUUSD: {lot:.2f} lots")
    except ValueError:
        print("\n❌ Please enter valid numeric values only.")


if __name__ == "__main__":
    main()


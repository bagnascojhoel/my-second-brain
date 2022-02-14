#leetcode #development_career #elixir

Today, [[2022-02-14]], I will solve
- [Day of the Year](https://leetcode.com/problems/day-of-the-year/).
It took me 01:31:10, and the solution I came up with was:

```elixir
defmodule Solution do
  @spec day_of_year(date :: String.t) :: integer
  def day_of_year(date) do
    months = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
    dateParts = String.split(date, "-");
    year = Enum.fetch(dateParts, 0)
        |> elem(1)
        |> Integer.parse
        |> elem(0);
    month = Enum.fetch(dateParts, 1)
        |> elem(1)
        |> Integer.parse
        |> elem(0);
    day = Enum.fetch(dateParts, 2)
        |> elem(1)
        |> Integer.parse
        |> elem(0);
    
    result = Enum.take(months, month-1)
        |> Enum.with_index
        |> Enum.reduce(0, fn {qtdDays, index}, acc -> acc + qtdDays end)
    
    isPerfectlyDivisibleBy4 = (rem year, 4) == 0;
    isPerfectlyDivisibleBy100 = (rem year, 100) == 0;
    isLeapYear = cond do
                isPerfectlyDivisibleBy4 and isPerfectlyDivisibleBy100 -> 
                    (rem year, 400) == 0 
                isPerfectlyDivisibleBy4 and !isPerfectlyDivisibleBy100 ->
                     true      
                !isPerfectlyDivisibleBy4 ->
                     false
            end
                
    cond do
        isLeapYear and month > 2 ->
            result + day + 1
        true ->
            result + day
    end
  end
end

```
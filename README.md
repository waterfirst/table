# table
![gt](https://user-images.githubusercontent.com/40909985/205479517-0bb20d98-24d3-4288-925b-6638086588fb.jpg)
![dt](https://user-images.githubusercontent.com/40909985/205479559-7dfa90c7-ca8d-4458-8f26-8034570bbb8d.jpg)


library(gt)

start_date <- "2010-06-07"
end_date <- "2010-06-14"

sp500 %>%
  dplyr::filter(date >= start_date & date <= end_date) %>%
  dplyr::select(-adj_close) %>%
  gt() %>%
  tab_header(
    title = "S&P 500",
    subtitle = glue::glue("{start_date} to {end_date}")
  ) %>%
  fmt_date(
    columns = vars(date),
    date_style = 3
  ) %>%
  fmt_currency(
    columns = vars(open, high, low, close),
    currency = "USD"
  ) %>%
  fmt_number(
    columns = vars(volume),
    suffixing = TRUE
  )

# load data ---------------------------------------------------------------

df <- tibble(
  x = runif(10),
  y = runif(10)
)
ggplot(df, aes(x, y)) +
  geom_point() +
  labs(
    x = quote(sum(x[i] ^ 2, i == 1, n)),
    y = quote(alpha + beta + frac(delta, theta))
  )


library(DT)
datatable(iris)

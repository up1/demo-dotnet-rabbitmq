FROM mcr.microsoft.com/dotnet/sdk:5.0-alpine AS build-env
WORKDIR /source
COPY *.csproj ./
RUN dotnet restore -r linux-musl-x64
COPY . ./
RUN dotnet publish -c release -o /app -r linux-musl-x64 --self-contained false 


FROM mcr.microsoft.com/dotnet/aspnet:5.0-alpine-amd64
WORKDIR /app
COPY --from=build-env /app .
ENTRYPOINT ["./ConsumerMq"]